
# 前言

<br>今天在Ubuntu界面关机时，将其放在包里。但由于ubuntu的长时间没有完成关机操作（黑屏），所以一直保持运行而发热，当我两小时后打开电脑包，直接被烫到手了。

<br>真的非常害怕，电脑硬盘再次因为高温而烧坏主板，导致数据丢失。半年前正是发生过这样的事，导致后果非常严重的数据财产损失。

<br>所以，这次必须要搞定ubuntu关机问题，以绝后患。

</br>

# 方法

### step 1 打开关机时的信息提示，找到错误

<br>- 备份/etc/default/grub `sudo cp /etc/default/grub /etc/default/grub.bak`

<br>- 打开/etc/default/grub文件，找到 `GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"`

<br>- 修改为`GRUB_CMDLINE_LINUX_DEFAULT="acpi=force"`

<br>- 保存后，在终端内执行命令`sudo update-grub`

<br>- 注：本次关机时仍无法显示关机信息，属正常现象。需再次开机时才会显示。

<br>  **显示关机信息后发现，关机卡死在黑屏界面的原因是出现了`A stop job is running for Snappy daemon...`问题，导致需要等待很长时间才会关机。下面要缩短关机的等待时间。**

</br>

### step 2 配置DefaultTimeoutStopSec

<br>- 打开终端，输入如下命令：`sudo vim /etc/systemd/system.conf`

<br>- 找到如下两行（大约在第35行左右）：`#DefaultTimeoutStartSec=90s`,`#DefaultTimeoutStopSec=90s`。将删除井号，缩短其数值，修改为`DefaultTimeoutStartSec=3s`,`DefaultTimeoutStopSec=3s`
<br>- 保存推出，执行命令`systemctl daemon-reload`使配置生效。

<br>- 重启即可

</br>

# 参考博客

<br>https://www.cnblogs.com/yann-qu/p/15590266.html