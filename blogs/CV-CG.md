## 一文搞懂-计算机视觉（CV）和计算机图形学（CG）

部分回答采取ai解释。

### 两者的形象比喻

> 计算机图形学——挤牙膏
> 
> 计算机视觉——吸牙膏


### 计算机视觉

**CV**: Computer Vision（计算机视觉）

计算机视觉的目标是让**计算机能够从图像或视频中获取有用的信息**，并对其进行理解和分析。具体任务包括：

> 1. **图像处理**：如滤波、边缘检测、颜色空间转换等。
> 2. **对象检测和识别**：如人脸检测、车牌识别、物体分类等。
> 3. **图像分割**：将图像划分为不同的区域或对象。
> 4. **特征提取和匹配**：如SIFT、ORB等特征点检测和匹配。
> 5. **三维重建**：从二维图像中重建三维场景。
> 6. **运动分析**：如光流计算、对象跟踪等。


### 计算机图形学
- **CG**: Computer Graphics（计算机图形学）

计算机图形学的目标是**生成和操作图像和图形**。具体任务包括：

> 1. **2D和3D图形生成**：如绘制基本图形、渲染3D模型等。
> 2. **几何变换**：如旋转、缩放、平移等。
> 3. **光照和着色**：模拟光照效果，使图像更真实。
> 4. **纹理映射**：将图像贴图应用于3D模型。
> 5. **动画**：生成和控制图形对象的动态变化。

## 常见相关领域的词汇解释

### CV

计算机视觉（Computer Vision）是一个快速发展的领域，涉及到图像处理、模式识别、机器学习和人工智能等多个学科。以下是一些常见的计算机视觉相关的英语简称：

#### 基本概念和技术

- **CV**: Computer Vision（计算机视觉）
- **AI**: Artificial Intelligence（人工智能）
- **ML**: Machine Learning（机器学习）
- **DL**: Deep Learning（深度学习）
- **CNN**: Convolutional Neural Network（卷积神经网络）
- **RNN**: Recurrent Neural Network（循环神经网络）
- **GAN**: Generative Adversarial Network（生成对抗网络）

#### 图像处理和分析

- **ROI**: Region of Interest（感兴趣区域）
- **SIFT**: Scale-Invariant Feature Transform（尺度不变特征变换）
- **SURF**: Speeded-Up Robust Features（加速稳健特征）
- **ORB**: Oriented FAST and Rotated BRIEF（方向FAST和旋转BRIEF）
- **HOG**: Histogram of Oriented Gradients（方向梯度直方图）
- **LBP**: Local Binary Patterns（局部二值模式）
- **MSER**: Maximally Stable Extremal Regions（最大稳定极值区域）

#### 目标检测和识别

- **YOLO**: You Only Look Once（一种实时目标检测系统）
- **SSD**: Single Shot MultiBox Detector（单次多框检测器）
- **R-CNN**: Region-based Convolutional Neural Network（基于区域的卷积神经网络）
- **Faster R-CNN**: 一种改进的R-CNN方法，具有更高的检测速度
- **Mask R-CNN**: 在Faster R-CNN基础上增加了实例分割功能

#### 视觉任务和应用

- **SLAM**: Simultaneous Localization and Mapping（同时定位与地图构建）
- **SFM**: Structure from Motion（运动结构）
- **MVS**: Multi-View Stereo（多视图立体）
- **OCR**: Optical Character Recognition（光学字符识别）
- **NLP**: Natural Language Processing（自然语言处理）

#### 图像和视频处理

- **DCT**: Discrete Cosine Transform（离散余弦变换）
- **FFT**: Fast Fourier Transform（快速傅里叶变换）
- **DWT**: Discrete Wavelet Transform（离散小波变换）
- **HDR**: High Dynamic Range（高动态范围）
- **PSNR**: Peak Signal-to-Noise Ratio（峰值信噪比）
- **SSIM**: Structural Similarity Index（结构相似性指数）

#### 数据集和评估

- **COCO**: Common Objects in Context（一个常用的图像数据集）
- **PASCAL VOC**: PASCAL Visual Object Classes（一个常用的视觉对象分类数据集）
- **ImageNet**: 一个大型视觉数据库，用于视觉对象识别软件研究
- **mAP**: Mean Average Precision（平均精度均值）
- **IoU**: Intersection over Union（交并比）

#### 其他相关术语

- **API**: Application Programming Interface（应用程序编程接口）
- **SDK**: Software Development Kit（软件开发工具包）
- **GPU**: Graphics Processing Unit（图形处理单元）
- **TPU**: Tensor Processing Unit（张量处理单元，Google开发的专用AI加速器）

了解这些简称和术语有助于更好地理解和应用计算机视觉技术，特别是在阅读相关文献、使用软件工具和进行项目开发时。



## CG

在计算机图形学领域，有许多常用的英语简称和术语。以下是一些常见的计算机图形学相关的英语简称：

### 基本概念和技术

- **CG**: Computer Graphics（计算机图形学）
- **GPU**: Graphics Processing Unit（图形处理单元）
- **API**: Application Programming Interface（应用程序编程接口）
- **DCC**: Digital Content Creation（数字内容创作）

### 几何变换

- **2D**: Two-Dimensional（二维）
- **3D**: Three-Dimensional（三维）
- **4D**: Four-Dimensional（四维）
- **VR**: Virtual Reality（虚拟现实）
- **AR**: Augmented Reality（增强现实）
- **MR**: Mixed Reality（混合现实）

### 渲染技术

- **RT**: Ray Tracing（光线追踪）
- **GI**: Global Illumination（全局光照）
- **BRDF**: Bidirectional Reflectance Distribution Function（双向反射分布函数）
- **HDR**: High Dynamic Range（高动态范围）
- **SSAO**: Screen Space Ambient Occlusion（屏幕空间环境光遮蔽）
- **PBR**: Physically Based Rendering（基于物理的渲染）

### 动画技术

- **IK**: Inverse Kinematics（逆向运动学）
- **FK**: Forward Kinematics（正向运动学）
- **LOD**: Level of Detail（细节层次）
- **MOCAP**: Motion Capture（动作捕捉）

### 图形API和标准

- **OpenGL**: Open Graphics Library（开放图形库）
- **DirectX**: Direct Extended（微软的图形API）
- **Vulkan**: 一种现代的高性能图形和计算API
- **HLSL**: High-Level Shading Language（高级着色语言）
- **GLSL**: OpenGL Shading Language（OpenGL着色语言）
- **CUDA**: Compute Unified Device Architecture（统一计算设备架构，NVIDIA的并行计算平台）

### 图形文件格式

- **OBJ**: 一种常见的3D模型格式
- **FBX**: Filmbox，一种常见的3D模型和动画格式
- **PNG**: Portable Network Graphics（便携式网络图形）
- **JPEG**: Joint Photographic Experts Group（联合图像专家组）

### 其他相关术语

- **GUI**: Graphical User Interface（图形用户界面）
- **UX**: User Experience（用户体验）
- **DPI**: Dots Per Inch（每英寸点数，用于描述图像的分辨率）

这些简称在计算机图形学的文献、软件开发和日常交流中非常常见，了解它们有助于更好地理解和应用计算机图形学的知识和技术。