# Phishing Detection Using Variational Autoencoder and ResNeXt-GRU

This project implements a phishing detection system using a combination of URL feature extraction, data augmentation with Variational Autoencoders (VAE), and classification with a ResNeXt-GRU architecture. The model is designed to identify phishing websites by analyzing URL characteristics and improving prediction accuracy with advanced machine learning techniques.

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset Description](#dataset-description)
- [Data Preprocessing](#data-preprocessing)
- [Data Augmentation](#data-augmentation)
- [Feature Extraction](#feature-extraction)
- [Model Architecture](#model-architecture)
- [Model Training & Optimization](#model-training--optimization)
- [Installation](#installation)

## Project Overview

The goal of this project is to develop a robust phishing detection model capable of distinguishing between legitimate and phishing websites. The system uses a combination of handcrafted feature extraction from URLs and advanced deep learning techniques to achieve high classification accuracy.

## Dataset Description

The dataset used for this project contains 48 features extracted from both phishing and legitimate websites, along with a class label indicating whether the website is phishing or legitimate. These features capture various aspects of the URL structure and the HTML content, providing a comprehensive basis for phishing detection.

## Data Preprocessing

- **Shuffling and Duplicate Removal:** The dataset is shuffled to mitigate bias, and duplicates are removed to maintain data integrity.
- **Standard Scaling:** Features are standardized to have a mean of 0 and a standard deviation of 1 using z-score normalization to ensure consistent scaling across features.

## Data Augmentation

A Variational Autoencoder (VAE) is used for data augmentation to generate additional synthetic samples. The VAE consists of an encoder and decoder network, enabling the generation of diverse and realistic samples from the learned latent space.

## Feature Extraction

Features are extracted from URLs using a combination of URL parsing and K-Nearest Neighbors (KNN):

- **URL Parsing:** Extracts 25 features based on URL structure and content.
- **K-Nearest Neighbors:** Complements URL parsing by generating 23 additional features using feature imputation based on nearest neighbors.

## Model Architecture

The phishing detection model utilizes a novel ResNeXt-GRU architecture, which combines ResNeXt blocks with Gated Recurrent Units (GRU):

- **ResNeXt Block:** Enriches feature representation through parallel convolutional pathways.
- **GRU Layer:** Captures temporal dependencies in data, facilitating robust feature learning.

## Model Training & Optimization

- **Optimizer:** Adam optimizer is used for efficient gradient descent.
- **Loss Function:** Cross Entropy Loss guides the model towards better classification accuracy.
- **Training Statistics:** The training process tracks loss and accuracy metrics to monitor model performance and guide adjustments.

## Installation

To run this project, clone the repository and install the required dependencies:

```bash
git clone https://github.com/yourusername/phishing-detection.git
cd phishing-detection
pip install -r requirements.txt
