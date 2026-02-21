# 前言

2026年春晚，机器人大放异彩。毫无疑问，具身智能（Embodied AI）绝对是未来的技术风口与科技热潮。作为一名普通的计算机科学专业的学生，我渴望跨入具身智能的大门，领略该领域的独特魅力。在向上海大学相关研究方向的学长学姐请教后，他们建议新手可以从开源的 LeggedGym 入手。然而经过调研，我发现 LeggedGym 已经停止更新。目前，NVIDIA 推出的 Isaac Sim 与 Isaac Lab 才是业内最前沿的开发生态。因此，我决定在自己的笔记本电脑上挑战部署这套环境，并通过运行基础项目来正式开启我的具身智能之旅。

<br>![](2602-lsaac-deploy.assets\2026-02-21_13-54-54.png)

# 前期工作

Isaac Sim 是底层强大的物理仿真引擎，负责提供高精度的物理计算与真实的 RTX 光线追踪渲染；而 Isaac Lab 则是构建在其上的应用层框架，专门为机器人强化学习设计，提供了极为便捷的 Python API。简而言之，Sim 是底层的引擎，Lab 则是供我们训练智能体的操作台。

根据官方文档，在原生 Windows 系统下通过纯 pip 部署底层 Isaac Sim 引擎，是目前最受推崇的方式。这种做法极大地降低了入门门槛，让我们无需单独下载几十GB的重量级独立应用程序，直接在代码环境内就能搞定一切。以下是我的核心部署流程与踩坑记录：

# 部署过程

**1. 基础环境搭建与底层引擎安装**

首先，我在 Windows 下使用 Conda 创建了一个全新的 Python 3.11 虚拟环境。激活环境后，直接通过 pip 指令拉取并安装 Isaac Sim 的核心引擎以及匹配的深度学习框架。纯 pip 的方式不仅省去了繁琐的软件安装包，还让依赖隔离变得更加清爽。

```bash
# 创建并激活 Conda 环境
conda create -n isaac python=3.11
conda activate isaac

# 升级 pip 并安装 Isaac Sim 底层引擎
python -m pip install --upgrade pip
pip install "isaacsim[all,extscache]==5.1.0" --extra-index-url https://pypi.nvidia.com

# 安装匹配系统的 PyTorch 基础包
pip install -U torch==2.7.0 torchvision==0.22.0 --index-url https://download.pytorch.org/whl/cu128

```

**2. 源码克隆与遭遇“依赖地狱”**

底层引擎安装完成后，我从 GitHub 克隆了 Isaac Lab 的官方源码仓库，准备进行上层框架的组装。

```bash
git clone https://github.com/isaac-sim/IsaacLab.git
cd IsaacLab

```

在尝试通过 `isaaclab.bat --install` 注册框架并运行官方测试脚本时，我遭遇了严重的依赖报错。这主要是由于底层的 Numpy 版本（被错误升级到 2.x）与内核发生冲突，以及 PyTorch 生态组件（如 torchaudio）的缺失。为了打破僵局，我放弃了让 pip 盲目自动解析，直接手动强行锁死了底层 C++ 内核所要求的兼容依赖版本。

```bash
# 强行降级 Numpy 并锁死底层内核依赖
pip install numpy==1.26.0 filelock==3.13.1 fsspec==2024.6.1 markupsafe==2.1.3 networkx==3.3 sympy==1.13.3 typing_extensions==4.12.2

# 补齐缺失的音频处理包，锁死 PyTorch 全家桶
pip install torch==2.7.0+cu128 torchvision==0.22.0+cu128 torchaudio==2.7.0+cu128 --extra-index-url https://download.pytorch.org/whl/cu128

# 解决 Web 服务的三角依赖冲突
pip install starlette==0.49.1 --upgrade fastapi

# 环境修复后，重新执行一键安装脚本
isaaclab.bat --install

```

**3. 显存危机与白屏闪烁排查**

环境彻底打通后，我迫不及待地使用官方指令去跑机器狗的强化学习测试项目：

```bash
# 运行机器狗训练代码
isaaclab.bat -p scripts/reinforcement_learning/rsl_rl/train.py --task=Isaac-Velocity-Rough-Anymal-C-v0

```

图形界面确实成功加载出来了，但随之而来的是画面疯狂的白色闪烁。经过排查，发现罪魁祸首是我笔记本的 RTX 3060 显卡仅有约 6GB 显存。默认启用的高级路径追踪渲染瞬间撑爆了 VRAM，导致材质数据在显存和普通内存间频繁吞吐。

解决办法也很直接：在弹出的 3D 视口菜单中，将渲染模式从极度吃显存的 Path Tracing 强制修改为 `RTX - Real-Time`（实时渲染），并适当调整了 DLSS 策略，画面的闪烁问题瞬间迎刃而解。

**4. 最终实战：推车倒立摆 (CartPole)**

在摸清了硬件极限和渲染配置后，我转而开始训练经典的推车倒立摆项目。为了进一步节省宝贵的显存，我在训练阶段大幅降低了并行环境的数量，并坚决采用了无头模式（Headless）进行纯后台运算。

```bash
# 安装 RSL-RL 算法库
isaaclab.bat -i rsl_rl

# 启动推车倒立摆训练 (限制并行环境数量为 64，开启无头模式)
isaaclab.bat -p scripts\reinforcement_learning\rsl_rl\train.py --task Isaac-Cartpole-v0 --headless --num_envs 64

```

经过一段时间的迭代，模型顺利收敛。随后通过可视化推理命令，我成功渲染出了 CartPole 稳稳立住的画面。

```bash
# 渲染训练成果 (缩减渲染环境数量至 16)
isaaclab.bat -p scripts\reinforcement_learning\rsl_rl\play.py --task Isaac-Cartpole-v0 --num_envs 16

```

附上运行成功的gif图：

<br>![](2602-lsaac-deploy.assets/2026-02-21_12-24-28.gif)

# 感想

这次在受限的笔记本硬件上成功部署前沿的物理仿真框架，不仅让我对具身智能的算力分配与数据闭环有了非常直观的认识，更极大地锤炼了我排查底层系统依赖冲突的工程落地能力。万事开头难，但只要敢于动手折腾，这绝对是我迈向新领域极具价值的一步。

# 参考教程

> [探索Isaac Lab强化学习：推车倒立摆（CartPole）_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV11J8ezaE5C/?t=0)

> [[中配]Isaac Sim & Isaac Lab：机器人构建与训练完全指南 - Nikodem Bartnik_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1SSScBrEeN/)
