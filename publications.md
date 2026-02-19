---
layout: page
permalink: /publications/index.html
title: Publications
---

> Update: February 18th, 2026

## Academic Research

### Research Focus

- AIGC for fashion intelligence
- Diffusion-based controllable generation
- Garment understanding and pattern generation

### iRetexturing: Intelligent Fashion Items Retexturing via Diffusion Models

- **Venue:** *Textile Research Journal*, 2025
- **Authors:** <u>Yarui Zhang</u>, Yao Jin, Xin Huang
- **DOI:** [10.1177/00405175251356681](https://doi.org/10.1177/00405175251356681)
- **Webpage:** [Textile Research Journal - SAGE](https://journals.sagepub.com/doi/10.1177/00405175251356681)
- **National Invention Patent Certificate:** [View Certificate](/file/%E5%8F%91%E6%98%8E%E4%B8%93%E5%88%A9%E8%AF%81%E4%B9%A6-2025109124972.pdf)
- **Software Copyright Certificate:** [View Certificate](/file/%E8%BD%AF%E8%91%97%E8%AF%81%E4%B9%A6-2025SR1327298.pdf)


<br>![](/images/publications/iRetexturing.png)

**Summary:** iRetexturing addresses photorealism and structural consistency in fashion item retexturing through a three-stage framework: high-resolution preprocessing, quadripartite texture synthesis, and ControlNet-guided diffusion with Canny/depth constraints.

**Results:** On 4,400 fashion images, the method outperforms DiffuseIT with **LPIPS = 0.1385** and **SSIM = 0.8323**, narrowing the gap between conceptual design and production-ready assets.

### Example-based Approach for Automatic Garment Pattern Generation

- **Venue:** *Textile Research Journal*, 2025
- **Authors:** Roujia Hong, <u>Yarui Zhang</u>, Qi Zhang, Diqing Qian, Yao Jin, Huaxiong Zhang, Lili He
- **DOI:** [10.1177/00405175251358497](https://doi.org/10.1177/00405175251358497)
- **Webpage:** [Textile Research Journal - SAGE](https://journals.sagepub.com/doi/10.1177/00405175251358497)

<br>![](/images/publications/pattern-generation.png)

**Summary:** This work proposes an automated, example-based pipeline for generating 2D garment patterns from 3D meshes, combining a sparse graph transformer for panel segmentation and manufacturing constraints (symmetry + boundary smoothness) via hybrid B-spline fitting.

**Results:** The method achieves **99.99% segmentation accuracy** on a self-constructed dataset and **100% structural similarity** to target pattern templates.


---

## Practical Projects

### Haier Home Appliances KV Products Indian Style Background Image Generation Workflow (Internship)

<img src="/images/publications/haier.png" class="floatpic" width="260" height="180" style="float: right;">

- **Role:** AIGC workflow developer (intern)
- **Context:** Zhejiang University Artificial Intelligence Industrial Park Internship Program, Hangzhou ZAOWUYUN Technology Co.
- **Contributions:**
	- Built standardized KV generation workflow for home-appliance product visuals
	- Completed dataset labeling and SDXL-based background LoRA training for multiple categories
	- Independently developed set-length workflow and prompt templates
	- Built Flux-based human-object light/shadow interaction workflow in phase II
- **Outcome:** direct KV output rate up to **75%**
- **Tech Stack:** ComfyUI, AIGC, Stable Diffusion, Flux, image algorithms


### Sketch-based Garment Image Generation Algorithm Implementation (Undergraduate Mentor Project)

In an undergraduate mentor project, I implemented garment image generation from sketch outlines and texture patches. The project involved Linux-based experimentation and reproduction of state-of-the-art methods (including StyleGAN-family approaches) for data processing and image generation.

- **Tech Stack:** Python, PyTorch, Linux, deep learning, image algorithms

<center>
<img src="/images/publications/FFT.png">
</center>

### Multimodal Marine Document QA System based on RAG (Self-initiated Project) 

- **Project Overview:** Built a maritime-domain RAG system using LLM + FAISS vector database, supporting cross-corpus retrieval over industry documents and academic papers, incremental indexing updates, and citation-level traceability (file name / page number).
- **Key Highlight:** Integrated VLM and LangGraph to optimize the multimodal RAG pipeline for marine engineering scenarios, significantly reducing long-tail hallucinations and improving evidence-grounded cross-modal tracing.
- **Outcome:** Project has been open-sourced: [github.com/zyrzjyzxy/Sea-RAG](https://github.com/zyrzjyzxy/Sea-RAG)


### Automated ICL Evaluation System with Multimodal Logical Reasoning (Internship Project) 

- **Project Overview:** Contributed to ByteDance **Doubao-seed-1.8** project, focusing on a VLM-based automatic question generation and verification system.
- **Key Work:** Designed visual-difficulty and logical-difficulty dimensions, improved question quality through parameterized control and visual difficulty enhancement, and derived robust generation settings via stress testing.
- **Final Result:** Increased ICL question generation success rate from **10% to 40%**, delivering high-quality datasets aligned with business requirements for the SEED technical team and effectively supporting model training and iterative performance optimization.


### Fully Automated Data Annotation and Asset Repository Construction based on LLM Agent (Internship Project) 

- **Project Overview:** Built a vision-understanding agent with GPT-4o API to achieve fully automated semantic annotation and classification for large-scale image batches.
- **Key Work:** Developed Selenium-based automation scripts for high-quality image crawling from platforms such as ZCOOL, built a standardized asset repository, established a multilingual label schema, and designed multi-round feedback optimization to improve annotation accuracy and consistency.
- **Final Result:** Significantly reduced manual annotation costs and provided high-quality data support for downstream model fine-tuning.

