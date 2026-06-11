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

| Property         | Value             |
|------------------|-------------------|
| Total images     | 27,000            |
| Image size       | 64 × 64 pixels    |
| Channels         | RGB               |
| Land-use classes | 10                |
| Source           | Sentinel-2 (ESA)  |

A random rectangular region of each image is masked during preprocessing, following the procedure described in the assignment notebook.

> 💡 The dataset is loaded directly via `tensorflow_datasets` — no manual download required.

---

## ⚙️ Methodology

| Step | Component | Description |
|------|-----------|-------------|
| 1 | **Input** | Original image (64×64 RGB) |
| 2 | **Random Mask** | Rectangular region zeroed out |
| 3 | **Encoder (Conv2D)** | Extracts features from visible regions |
| 4 | **Bottleneck (Latent)** | Compressed representation |
| 5 | **Decoder (Conv2DTranspose)** | Reconstructs full image |
| 6 | **Output** | Reconstructed image (64×64 RGB) |

**Pipeline steps:**
1. Load and normalise EuroSAT RGB images
2. Apply random rectangular masks to each image
3. Train encoder-decoder model to reconstruct masked regions
4. Evaluate visually by comparing original, masked, and reconstructed outputs
---

## 🧠 Model Architecture

| Component     | Details                                      |
|---------------|----------------------------------------------|
| Architecture  | Convolutional Encoder-Decoder (U-Net style)  |
| Loss Function | Mean Squared Error (MSE)                     |
| Optimizer     | Adam                                         |
| Input size    | 64 × 64 × 3                                  |
| Framework     | TensorFlow / Keras                           |
| Hardware      | GPU recommended (Colab/Jupyter)              |

---

## 📊 Results

The trained model successfully reconstructs missing image regions with visually consistent outputs. Example outputs — including side-by-side comparisons of original, masked, and reconstructed images — are included in the notebook.

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install -r requirements.txt
```

### Run

```bash
# 1. Clone the repository
git clone https://github.com/FarhadBayrami/image-inpainting-eurosat-DL-Course.git
cd image-inpainting-eurosat-DL-Course

# 2. Install dependencies
pip install -r requirements.txt

# 3. Launch the notebook
jupyter notebook Inpainting.ipynb
```

> 💡 **Tip:** The EuroSAT dataset loads automatically via `tensorflow_datasets` — no manual download needed. For faster training use Google Colab: *Runtime → Change runtime type → GPU*.

---

## 📁 Project Structure

| File | Description |
|------|-------------|
| `Inpainting.ipynb` | Full pipeline: data, masking, model, training, visualisation |
| `requirements.txt` | Python dependencies |
| `LICENSE` | MIT License |
| `CITATION.cff` | How to cite this work |
| `README.md` | Project documentation |

## 🔮 Future Work

- [ ] Experiment with U-Net skip connections for sharper reconstructions
- [ ] Apply irregular/free-form masks (more realistic than rectangular)
- [ ] Add perceptual loss (VGG-based) alongside MSE
- [ ] Extend to multispectral (13-band) EuroSAT data
- [ ] Evaluate on cloud-removal benchmarks (SEN2-MTC, RICE dataset)

---

## 📚 References

1. Helber, P. et al. — *EuroSAT: A Novel Dataset and Deep Learning Benchmark for Land Use and Land Cover Classification*, IEEE JSTARS, 2019.
2. Pathak, D. et al. — *Context Encoders: Feature Learning by Inpainting*, CVPR, 2016.
3. ESA Sentinel-2 Mission — [sentinel.esa.int](https://sentinel.esa.int/web/sentinel/missions/sentinel-2)

---

## 👤 Author

**Farhad Bayrami**
MSc Student — University of Bologna
📧 [farhad.bayrami@studio.unibo.it](mailto:farhad.bayrami@studio.unibo.it)
🔗 [GitHub](https://github.com/FarhadBayrami)

---

<div align="center">
  <sub>Built with ❤️ as part of a Deep Learning course project at the University of Bologna · February 2025</sub>
</div>