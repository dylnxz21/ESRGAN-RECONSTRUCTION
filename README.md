# Brain MRI Super-Resolution using ESRGAN

<p align="center">
  <img src="images/mri_super_resolution_result.png" width="700">
</p>

## Overview

This project explores deep learning techniques for improving the resolution of brain MRI images using **Enhanced Super-Resolution Generative Adversarial Networks (ESRGAN)**.

The main objective is to reconstruct high-resolution MRI images from low-resolution inputs while preserving important anatomical structures and improving image quality.

This work was developed during my research internship on:

**"Synthetic MRI Generation and Super-Resolution Techniques"**

The project combines medical image processing, deep learning, and quantitative evaluation methods to investigate MRI super-resolution approaches.

---

# Objectives

The main objectives of this project are:

- Improve spatial resolution of MRI images
- Explore GAN-based super-resolution techniques
- Reconstruct high-resolution MRI images from degraded inputs
- Compare reconstructed images with original high-resolution references
- Evaluate reconstruction quality using quantitative metrics

---

# Research Context

This project was developed during a **150-hour research internship** focused on:

**Synthetic MRI Generation and Super-Resolution Techniques**

The research activities included:

- Reviewing scientific literature on MRI reconstruction and generative models
- Processing and analyzing medical imaging data
- Exploring deep learning approaches for image enhancement
- Implementing and evaluating MRI super-resolution methods

The goal was to investigate how artificial intelligence techniques can improve medical imaging quality and assist image analysis workflows.

---

# Technologies Used

| Category | Tools |
|-|-|
| Programming Language | Python |
| Deep Learning Framework | PyTorch |
| MRI Processing | NiBabel, NiTorch |
| Data Format | NIfTI (.nii) |
| Environment | Google Colab |
| GPU Acceleration | CUDA |
| Evaluation Metrics | MSE, Image Visualization |

---

# Dataset

The experiments were performed using simulated brain MRI data from:

**BrainWeb MRI Dataset**

The dataset contains simulated brain images with different MRI modalities.

Used modalities:

- T1-weighted MRI
- T2-weighted MRI
- Proton Density (PD)

Data format:


.nii (NIfTI)


The dataset was used to create low-resolution MRI images through simulated degradation before applying super-resolution reconstruction.

---

# Methodology

The workflow consists of the following steps:


High Resolution MRI
|
↓
Data Preprocessing
|
↓
Degradation Model
|
↓
Low Resolution MRI
|
↓
ESRGAN Reconstruction
|
↓
Super-Resolution MRI
|
↓
Evaluation


## Workflow Description

### 1. MRI Data Loading

MRI volumes are loaded from NIfTI files and prepared for processing.

### 2. Image Degradation

A degradation model is applied to simulate lower-resolution MRI acquisitions.

The degradation process includes:

- Spatial resolution reduction
- Downsampling
- Noise simulation

### 3. Super-Resolution Reconstruction

The degraded MRI images are processed using ESRGAN to reconstruct higher-resolution images.

### 4. Evaluation

The reconstructed images are compared with original high-resolution references using quantitative metrics.

---

# Model Architecture

This project investigates the use of **Enhanced Super-Resolution Generative Adversarial Networks (ESRGAN)**.

ESRGAN is composed of two main networks:

## Generator Network

The generator learns how to reconstruct high-resolution MRI images from low-resolution inputs.

Main components:

- Residual-in-Residual Dense Blocks (RRDB)
- Deep feature extraction
- High-resolution image reconstruction

## Discriminator Network

The discriminator evaluates whether generated images are realistic compared with original MRI images.

The training process uses:

- Reconstruction loss
- Adversarial loss
- Feature-based optimization

Architecture:


Low Resolution MRI
|
↓
ESRGAN Generator
|
↓
Super Resolution MRI
|
↓
ESRGAN Discriminator
|
↓
Image Quality Evaluation


---

# Project Structure


Brain-MRI-Super-Resolution/

│
├── README.md
├── requirements.txt
│
├── notebooks/
│ └── MRI_super_resolution.ipynb
│
├── src/
│ ├── preprocessing.py
│ ├── degradation.py
│ ├── model.py
│ ├── train.py
│ └── evaluation.py
│
├── data/
│ └── README.md
│
├── results/
│ ├── figures/
│ └── metrics.csv
│
└── models/
└── esrgan_weights.pth


---

# Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/Brain-MRI-Super-Resolution.git

Move into the project directory:

cd Brain-MRI-Super-Resolution

Create a virtual environment:

python -m venv venv

Activate the environment.

Windows:

venv\Scripts\activate

Linux/Mac:

source venv/bin/activate

Install dependencies:

pip install -r requirements.txt
Usage
1. Data Preparation

Prepare MRI volumes in NIfTI format:

.nii files

Supported modalities:

T1
T2
Proton Density (PD)
2. Generate Low Resolution MRI Images

Apply the degradation model to simulate lower-resolution MRI scans.

The generated images are used as inputs for the super-resolution model.

3. Run Super-Resolution Reconstruction

The ESRGAN model processes low-resolution MRI images and generates enhanced resolution outputs.

Input:

Low Resolution MRI

Output:

Super Resolution MRI
4. Evaluate Results

The reconstructed MRI images are compared with ground-truth high-resolution images.

Results

The reconstruction performance was evaluated using:

Mean Squared Error (MSE)

Method	MSE
Trilinear Interpolation	35226.24
ESRGAN Super-Resolution	28604.69

The ESRGAN-based reconstruction achieved a lower reconstruction error compared with traditional interpolation methods.

This indicates improved recovery of image details from low-resolution MRI inputs.

Results Visualization

The reconstruction process can be visualized by comparing:

Original high-resolution MRI
Low-resolution MRI after degradation
ESRGAN reconstructed MRI

Example:

Original MRI
      |
      ↓
Low Resolution MRI
      |
      ↓
ESRGAN Reconstruction
      |
      ↓
Evaluation

Visualization results are stored in:

results/figures/
Evaluation Metrics

The project currently evaluates reconstruction quality using:

Mean Squared Error (MSE)

MSE measures the average squared difference between reconstructed and reference images.

Lower MSE values indicate better reconstruction accuracy.

Future evaluations can include:

Peak Signal-to-Noise Ratio (PSNR)
Structural Similarity Index (SSIM)
Limitations

Current limitations include:

Experiments were performed using simulated MRI data
Deep learning training requires significant computational resources
Limited GPU availability affected large-scale ESRGAN training
Further validation with clinical MRI datasets is required
Future Work

Possible improvements include:

Training ESRGAN on larger medical imaging datasets
Comparing ESRGAN with diffusion-based super-resolution models
Adding PSNR and SSIM evaluation metrics
Improving 3D volumetric MRI reconstruction
Exploring synthetic MRI generation using generative AI models
References
Wang, X. et al.
ESRGAN: Enhanced Super-Resolution Generative Adversarial Networks
2018
McGill University
BrainWeb: Simulated Brain Database
Ho, J. et al.
Denoising Diffusion Probabilistic Models
2020
Author

Shami Robin Dylan

Data Analysis Student
University of Messina, Italy

Research Internship:

Synthetic MRI Generation and Super-Resolution Techniques


# Key Findings

The experiments showed that ESRGAN-based reconstruction reduced reconstruction error compared with traditional interpolation methods.

Main observations:

- ESRGAN recovered more detailed structures compared with simple interpolation
- Deep learning approaches improved MRI resolution reconstruction
- Quantitative evaluation demonstrated lower MSE values
- Medical image super-resolution requires careful validation to preserve anatomical accuracy
