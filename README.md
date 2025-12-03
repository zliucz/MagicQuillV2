# 🪶 MagicQuill V2: Precise and Interactive Image Editing with Layered Visual Cues

  <a href="https://magicquill.art/v2/"><img src="https://img.shields.io/static/v1?label=Project&message=magicquill.art/v2&color=blue"></a>
  <a href="https://arxiv.org/abs/2512.03046"><img src="https://img.shields.io/badge/arxiv-2512.03046-b31b1b.svg"></a>
  <a href="https://huggingface.co/spaces/AI4Editing/MagicQuillV2"><img src="https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Spaces-blue"></a>
  <a href="https://creativecommons.org/licenses/by-sa/4.0/"><img src="https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg"></a>
</div>

<br>

<div align="center">
  <video src="https://github.com/user-attachments/assets/58079152-7729-48ed-9bb4-0ddfd1873dd0" width="100%" controls autoplay muted loop></video>
</div>

<br>

<div align="center">

**[Zichen Liu](https://zliucz.github.io/)**<sup>\*,1,2</sup>, **[Yue Yu](https://bruceyy.com/)**<sup>\*,1,2</sup>, **[Hao Ouyang](https://ken-ouyang.github.io/)**<sup>2</sup>, **[Qiuyu Wang](https://github.com/qiuyu96)**<sup>2</sup>, **[Shuailei Ma](https://scholar.google.com/citations?user=dNhzCu4AAAAJ&hl)**<sup>2,3</sup>, **[Ka Leong Cheng](https://felixcheng97.github.io/)**<sup>2</sup>, **[Wen Wang](https://github.com/encounter1997)**<sup>2,4</sup>, **[Qingyan Bai](http://bqy.info/)**<sup>1,2</sup>, **[Yuxuan Zhang](https://scholar.google.com/citations?user=f2VoRWYAAAAJ&hl)**<sup>5</sup>, **[Yanhong Zeng](https://zengyh1900.github.io/)**<sup>2</sup>, **[Yixuan Li](https://yixuanli98.github.io/)**<sup>2,5</sup>, **[Xing Zhu](https://openreview.net/profile?id=~Xing_Zhu2)**<sup>2</sup>, **[Yujun Shen](https://shenyujun.github.io/)**<sup>2</sup>, **[Qifeng Chen](http://cqf.io/)**<sup>1</sup>

<sup>1</sup>HKUST <sup>2</sup>Ant Group <sup>3</sup>NEU <sup>4</sup>ZJU <sup>5</sup>CUHK <br>
<small><sup>*</sup> Equal Contribution</small>

</div>

> **TLDR:** MagicQuill V2 introduces a layered composition paradigm to generative image editing, disentangling creative intent into controllable visual cues (Content, Spatial, Structural, Color) for precise and intuitive control.

- [🪶 MagicQuill V2: Precise and Interactive Image Editing with Layered Visual Cues](#-magicquill-v2-precise-and-interactive-image-editing-with-layered-visual-cues)
  - [TODO List](#todo-list)
  - [Update Log](#update-log)
  - [Hardware Requirements](#hardware-requirements)
  - [Setup](#setup)
  - [System Overview](#system-overview)
  - [Tutorial](#tutorial)
  - [Citation](#citation)
  - [Acknowledgement](#acknowledgement)

## TODO List

- [✅] Release the paper and project page.
- [✅] Release the system with UI.
- [✅] Release gradio demo on HuggingFace.
- Release the batch inference code.
- Release the training code.

## Update Log

- [2025.12.03] 📢 **MagicQuill V2** is released!
- [Legacy] For the previous version (**MagicQuill V1**), which requires much less VRAM and computation resources, please visit [MagicQuill V1 Repository](https://github.com/ant-research/MagicQuill).

## Hardware Requirements

Our model is based on Flux Kontext, which is large and computationally intensive.
- **VRAM**: Approximately **40GB** of VRAM is required for inference.
- **Speed**: It takes about **30 seconds** to generate a single image.

> **Important**: This is a research project focused on pushing the boundaries of interactive editing. If you do not have sufficient GPU memory, we recommend checking out our [**MagicQuill V1**](https://github.com/ant-research/MagicQuill) or trying the online demo on [**Hugging Face Spaces**](https://huggingface.co/spaces/AI4Editing/MagicQuillV2).

## Setup

1.  **Clone the repository**
    ```bash
    git clone https://github.com/magic-quill/MagicQuillV2.git
    cd MagicQuillV2
    ```

2.  **Create environment**
    ```bash
    conda create -n MagicQuillV2 python=3.10 -y
    conda activate MagicQuillV2
    ```

3.  **Install dependencies**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Download models**
    Download the models from [Hugging Face](https://huggingface.co/LiuZichen/MagicQuillV2-models) and place them in the `models/` directory.

    ```bash
    huggingface-cli download LiuZichen/MagicQuillV2-models --local-dir models
    ```

5.  **Run the demo**
    ```bash
    python app.py
    ```

## System Overview

The MagicQuill V2 interactive system is designed to unify our layered composition framework.

<div align="center">
  <img src="./assets/V2_UI.png" alt="MagicQuill V2 UI" width="100%">
</div>

### Key Upgrades from V1

1.  **Toolbar (A)**: Features a new **Local Edit Brush** for defining the target editing area, along with tools for sketching edges and applying color.
2.  **Visual Cue Manager (B)**: Holds all content layer visual cues (**foreground props**) that users can drag onto the canvas to define what to generate.
3.  **Image Segmentation Panel (C)**: Accessed via the segment icon, this panel allows precise object extraction using SAM (Segment Anything Model) with positive/negative dots or bounding boxes.

## Tutorial

💡 **For a detailed guide on the 5 layer operations, please visit our [Project Page](https://magicquill.art/v2).**

## Citation

If you find MagicQuill V2 useful for your research, please cite our paper:

```bibtex
@article{liu2025magicquillv2,
  title={MagicQuill V2: Precise and Interactive Image Editing with Layered Visual Cues},
  author={Zichen Liu, Yue Yu, Hao Ouyang, Qiuyu Wang, Shuailei Ma, Ka Leong Cheng, Wen Wang, Qingyan Bai, Yuxuan Zhang, Yanhong Zeng, Yixuan Li, Xing Zhu, Yujun Shen, Qifeng Chen},
  journal={arXiv:2512.03046},
  year={2025}
}
```

## Acknowledgement

Our implementation builds upon several great open-source projects: 
- [EasyControl](https://github.com/haotian-liu/LLaVA)
- [ComfyUI](https://github.com/Xiaojiu-z/EasyControl)
- [comfyui_controlnet_aux](https://github.com/Fannovel16/comfyui_controlnet_aux)
- [fabric.js](https://github.com/fabricjs/fabric.js)
We thank the authors for their contributions.

**License**: This repo is governed by the license of CC BY-NC 4.0. We strongly advise users not to knowingly generate or allow others to knowingly generate harmful content.
