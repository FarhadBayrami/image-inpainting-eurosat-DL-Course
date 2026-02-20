# Image Inpainting using EuroSAT Dataset

## Project Overview
This project focuses on image inpainting, which consists of reconstructing missing or deteriorated parts of an image.

The goal is to train a deep learning model capable of restoring masked regions of satellite images.

## Dataset
The dataset used is the TensorFlow EuroSAT RGB dataset based on Sentinel-2 satellite images.

- Total images: 27,000
- Image size: 64x64
- Channels: RGB

A random portion of each image is masked following the procedure described in the assignment notebook.

## Methodology
The project includes:

- Data loading and preprocessing
- Random masking of image regions
- Model architecture design
- Training procedure
- Reconstruction of masked images
- Visualization of results

## Results
The trained model successfully reconstructs missing image regions with visually consistent outputs.

Example outputs and comparisons between original, masked, and reconstructed images are included in the notebook.

## File Structure
- `Inpainting.ipynb` → Complete implementation of the project

## Requirements
- Python 3.x
- TensorFlow
- NumPy
- Matplotlib

## Author
Farhad Bayrami

## Course
Deep Learning

## Submission Date
February 2023