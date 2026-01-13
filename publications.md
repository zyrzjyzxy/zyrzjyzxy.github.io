---
layout: page
permalink: /publications/index.html
title: Publications
---

> Update: January 14th , 2026


## Ongoing Project


<br>**iRetexturing: Intelligent Fashion Items Retexturing via Diffusion Models**

<br>- Authors: <u>Yarui Zhang</u>, Yao Jin, Xin Huang

<br>- Journal: Textile Research Journal, 2025 [PDF](/file/zhang-et-al-2025-iretexturing-intelligent-fashion-items-retexturing-via-diffusion-models.pdf)



<img src="/images/publications/iRetexturing.png" class="floatpic" width="260" height="180" style="float: right;">

<br>This paper introduces iRetexturing, a novel framework designed to address the challenges of photorealism and structural integrity in fashion item retexturing. The method utilizes a three-stage pipeline integrating diffusion models with geometric priors: high-resolution preprocessing via masked super-resolution and semantic segmentation, quadripartite texture synthesis for seamless pattern tiling, and ControlNet-guided diffusion employing dual spatial constraints (Canny edges and depth maps). Evaluation on 4,400 fashion images demonstrates that iRetexturing significantly outperforms state-of-the-art methods like DiffuseIT, achieving superior Perceptual Image Patch Similarity (LPIPS: 0.1385) and Structural Similarity (SSIM: 0.8323), effectively bridging the gap between conceptual prototypes and production-ready assets.


<br>**Patent Information:**  This work has resulted in a National Invention Patent [PDF](/file/ZL-2025109124972.pdf), which further validates the technical innovation and practical application potential of the iRetexturing framework in the fashion industry.

<br>**Example-based Approach for Automatic Garment Pattern Generation**

<br>- Authors: Roujia Hong, <u>Yarui Zhang</u>, Qi Zhang, Diqing Qian, Yao Jin, Huaxiong Zhang, Lili He

<br>- Journal: Textile Research Journal, 2025 [PDF](/file/hong-et-al-2025-example-based-approach-for-automatic-garment-pattern-generation.pdf)


<img src="/images/publications/pattern-generation.png" class="floatpic" width="260" height="180" style="float: right;">

<br>This study proposes an automated, example-based method for generating 2D garment patterns from 3D meshes, addressing the industry's need for standardization and geometric fidelity. The approach features a Sparse Graph Transformer network that efficiently segments 3D garment meshes into individual panels by leveraging virtual node sparsification to reduce computational complexity. To ensure industrial viability, the framework integrates manufacturing constraints—specifically symmetry and boundary smoothness via hybrid B-spline fitting—into the flattening process. Experimental results show exceptional performance, with a segmentation accuracy of 99.99% on a self-constructed dataset and 100% structural similarity for generated patterns compared to templates, offering a robust solution for intelligent fashion manufacturing.


---

## Early Project


**Implementation of sketch-based algorithm for garment image generation**<br>

<br>In an undergraduate mentor project, garment images were generated using garment texture patches and sketch outlines. Multiple papers such as styleGAN and other cutting edge deep learning models were called based on Linux during the thesis implementation to implement the data processing and some of the image algorithms.

<br>Technology selection: Python, Pytorch, Linux, Deep Learning, Image Algorithms.

<br>Undergraduate Mentorship Projects

<center>
<img src="/images/publications/FFT.png">
</center>
<br>



<br>**Haier Home Appliances KV Products Indian Style Background Image Generation Workflow**<br>

<img src="/images/publications/haier.png" class="floatpic" width="260" height="180" style="float: right;">

<br>This project aims to develop a set of industrial-grade standardized AI for Haier Home Appliances series product effect images for the Indian market
Workflow. I completed data labeling for several home appliances and trained separate SDXL-based background
lora.

<br>I have independently developed the Haier home appliance workflow and home appliance set length drawing workflow, summarized the efficient project prompt template, and the straight-out KV drawing rate is as high as 75%.

<br>In the second phase of the project, independently developed Flux-based man-machine light and shadow interaction workflow, with the ability to perfect the drawing.

<br>Technology selection: ComfyUI, image algorithm, AIGC, Stable Diffusion, Flux.

<br>Zhejiang University Artificial Intelligence Industrial Park Internship Program Hangzhou ZAOWUYUN Technology Co.

<br>
