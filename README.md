# Pix2Pix Image Translation with cGAN
This repository implements an image-to-image translation model using a conditional Generative Adversarial Network (cGAN), specifically the Pix2Pix architecture. The implementation uses TensorFlow and is designed for the facades dataset.
# Overview
The project implements a Pix2Pix model that can translate architectural facade labels to photorealistic building facades. It uses a conditional GAN architecture where the generator creates images based on input conditions, and the discriminator evaluates both the input conditions and the generated images.
# Requirements
- TensorFlow
- Matplotlib
- Kaggle API
- Git

# Installation
- `pip install tensorflow matplotlib kaggle`
- `pip install git+https://github.com/tensorflow/examples.git`

# Dataset
The project uses the Pix2Pix Facades dataset, which can be downloaded from Kaggle. To set up the dataset:
- Configure your Kaggle API credentials
- Download the dataset:
  - `kaggle datasets download -d sabahesaraki/pix2pix-facades-dataset`
- Unzip the downloaded file to the project directory

# Model Architecture
- **Generator**
  - U-Net architecture with skip connections
  - Output channels: 3 (RGB)
  - Batch normalization for training stability

**Discriminator**

- PatchGAN architecture
- Evaluates image patches for more detailed feedback
- Uses batch normalization

# Training
The model is trained using:
- Adam optimizer (learning rate: 2e-4, β1: 0.5)
- Binary cross-entropy loss for adversarial component
- L1 loss for image reconstruction
- 50 epochs by default

# Loss Functions
- Generator Loss: Combination of adversarial loss and L1 loss
- Discriminator Loss: Binary cross-entropy on real and generated images

# Evaluation Metrics
The model's performance is evaluated using:
- Mean Absolute Error (MAE)
- Peak Signal-to-Noise Ratio (PSNR)

