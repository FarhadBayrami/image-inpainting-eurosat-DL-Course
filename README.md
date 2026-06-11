<div align="center">

# 🛰️ Image Inpainting on EuroSAT Satellite Imagery
### Deep Learning-Based Reconstruction of Masked Regions in Sentinel-2 RGB Images

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)](https://tensorflow.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

<p align="center">
  <img src="https://img.shields.io/badge/Dataset-EuroSAT%20RGB-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/Images-27%2C000-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Resolution-64x64-orange?style=flat-square"/>
</p>

*A deep learning model that reconstructs missing or corrupted regions in satellite images using the EuroSAT RGB dataset.*

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Dataset](#-dataset)
- [Methodology](#-methodology)
- [Model Architecture](#-model-architecture)
- [Results](#-results)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [Future Work](#-future-work)
- [References](#-references)
- [Author](#-author)

---

## 🔬 Overview

Image inpainting is the task of reconstructing missing, masked, or corrupted regions of an image in a visually plausible and semantically consistent way. This project applies inpainting to **satellite remote sensing imagery**, using the EuroSAT RGB dataset derived from ESA Sentinel-2 observations.

The model learns to restore randomly masked regions of land-use satellite images — a technique with practical applications in:
- Cloud removal from satellite imagery
- Restoration of corrupted remote sensing data
- Data augmentation for downstream classification tasks

---

## 📦 Dataset

**EuroSAT RGB** — via TensorFlow Datasets, based on ESA Sentinel-2 satellite imagery.

| Property        | Value             |
|-----------------|-------------------|
| Total images    | 27,000            |
| Image size      | 64 × 64 pixels    |
| Channels        | RGB               |
| Land-use classes| 10                |
| Source          | Sentinel-2 (ESA)  |

A random rectangular region of each image is masked during preprocessing, following the procedure described in the assignment notebook.

> 💡 The dataset is loaded directly via `tensorflow_datasets` — no manual download required.

---

## ⚙️ Methodology