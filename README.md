# Electronic Component Recognition Using Faster SqueezeNet

This repository contains the implementation of an electronic component recognition algorithm based on a custom **Faster SqueezeNet** deep learning model. The project aims to classify electronic components (such as capacitors, resistors, inductors, transistors, and ICs) with high accuracy and low computational complexity.

The work is inspired by the research paper:  
**"An Electronic Component Recognition Algorithm Based on Deep Learning with a Faster SqueezeNet"**  
by Yuanyuan Xu, Genke Yang, Jiliang Luo, and Jianan He, published in *Mathematical Problems in Engineering*, 2020.  
[Link to the paper](https://onlinelibrary.wiley.com/doi/full/10.1155/2020/2940286)

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Dataset](#dataset)
3. [Faster SqueezeNet Architecture](#faster-squeezenet-architecture)
4. [Simulation Process](#simulation-process)
5. [Challenges](#challenges)
6. [How to Run the Code](#how-to-run-the-code)
7. [Dependencies](#dependencies)
8. [License](#license)

---

## Project Overview

The goal of this project is to classify electronic components using a deep learning model. The **Faster SqueezeNet** model is used due to its lightweight architecture and high accuracy. The model is trained on the **Basic Electronic Components Dataset**, which contains images of **5 distinct types of components**:
- **Capacitors**
- **Resistors**
- **Inductors**
- **Transistors**
- **Integrated Circuits (ICs)**

The model is designed to achieve high accuracy while maintaining low computational complexity, making it suitable for real-time industrial applications.

---

## Dataset

The dataset used in this project is the **Basic Electronic Components Dataset**, available on Kaggle:  
[Basic Electronic Components Dataset on Kaggle](https://www.kaggle.com/datasets/julioazancort/basic-electronic-components)

### Dataset Structure
The dataset consists of **5 distinct folders**, each containing images of a specific electronic component:
1. **Capacitors**
2. **Resistors**
3. **Inductors**
4. **Transistors**
5. **Integrated Circuits (ICs)**

Each folder contains multiple images of the respective component, making it suitable for training and evaluating deep learning models.

### Preprocessing
The images are preprocessed as follows:
- Resized to **128×128 pixels** to reduce memory usage.
- Normalized to the range **[0, 1]**.
- Augmented using techniques like random rotation, flipping, and brightness adjustment to improve model generalization.

---

## Faster SqueezeNet Architecture

The **Faster SqueezeNet** model is a lightweight deep learning architecture designed for efficient image classification. Key features include:
1. **Fire Module**: Combines 1×1 and 3×3 convolutions to reduce the number of parameters.
2. **Residual Connections**: Inspired by ResNet, these connections help address vanishing gradients and degradation.
3. **Dense Connections**: Inspired by DenseNet, these connections enhance feature reuse and improve performance in early layers.
4. **Batch Normalization**: Added to ensure better convergence.

The model consists of:
- 1 BatchNorm layer
- 3 block layers
- 4 convolution layers
- 1 global average pooling layer

---

## Simulation Process

### 1. Data Preprocessing
Images are resized to **128×128 pixels**, and invalid images are filtered out using the `is_valid_image` function. The images are then normalized to the range **[0, 1]**.

### 2. Dataset Creation
A TensorFlow dataset is created using a generator function (`create_dataset`). The dataset is split into **training (70%)**, **validation (15%)**, and **test (15%)** sets.

### 3. Model Training
The Faster SqueezeNet model is built using the `build_faster_squeezenet` function. The model is compiled with the **Adam optimizer** and **sparse categorical cross-entropy loss**. Training is performed for **10 epochs**.

### 4. Evaluation
The model is evaluated on the test set to compute **accuracy**, **ROC-AUC**, **TPR**, and **FPR**.

---

## Challenges

Due to the large size of the model and dataset, running the code on **Google Colab** was not feasible. As a result, the model will be trained and evaluated in the **next branch** using a more powerful environment.
