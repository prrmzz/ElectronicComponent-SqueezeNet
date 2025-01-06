# ElectronicComponent-SqueezeNet
Electronic Component Recognition Using Faster SqueezeNet
This repository contains the implementation of an electronic component recognition algorithm based on a custom Faster SqueezeNet deep learning model. The project aims to classify electronic components (such as capacitors, resistors, inductors, transistors, and ICs) with high accuracy and low computational complexity.

The work is inspired by the research paper:
"An Electronic Component Recognition Algorithm Based on Deep Learning with a Faster SqueezeNet"
by Yuanyuan Xu, Genke Yang, Jiliang Luo, and Jianan He, published in Mathematical Problems in Engineering, 2020.
Link to the paper

Table of Contents
Project Overview

Dataset

Faster SqueezeNet Architecture

Simulation Process

Challenges

How to Run the Code

Dependencies

License

Project Overview
The goal of this project is to classify electronic components using a deep learning model. The Faster SqueezeNet model is used due to its lightweight architecture and high accuracy. The model is trained on the Basic Electronic Components Dataset, which contains images of 5 distinct types of components:

Capacitors

Resistors

Inductors

Transistors

Integrated Circuits (ICs)

The model is designed to achieve high accuracy while maintaining low computational complexity, making it suitable for real-time industrial applications.

Dataset
The dataset used in this project is the Basic Electronic Components Dataset, available on Kaggle:
Basic Electronic Components Dataset on Kaggle

Dataset Structure
The dataset consists of 5 distinct folders, each containing images of a specific electronic component:

Capacitors

Resistors

Inductors

Transistors

Integrated Circuits (ICs)

Each folder contains multiple images of the respective component, making it suitable for training and evaluating deep learning models.

Preprocessing
The images are preprocessed as follows:

Resized to 128×128 pixels to reduce memory usage.

Normalized to the range [0, 1].

Augmented using techniques like random rotation, flipping, and brightness adjustment to improve model generalization.

Faster SqueezeNet Architecture
The Faster SqueezeNet model is a lightweight deep learning architecture designed for efficient image classification. Key features include:

Fire Module: Combines 1×1 and 3×3 convolutions to reduce the number of parameters.

Residual Connections: Inspired by ResNet, these connections help address vanishing gradients and degradation.

Dense Connections: Inspired by DenseNet, these connections enhance feature reuse and improve performance in early layers.

Batch Normalization: Added to ensure better convergence.

The model consists of:

1 BatchNorm layer

3 block layers

4 convolution layers

1 global average pooling layer

Simulation Process
1. Data Preprocessing
Images are resized to 128×128 pixels.

Invalid images are filtered out using the is_valid_image function.

Images are normalized to the range [0, 1].

2. Dataset Creation
A TensorFlow dataset is created using a generator function (create_dataset).

The dataset is split into training (70%), validation (15%), and test (15%) sets.

3. Model Training
The Faster SqueezeNet model is built using the build_faster_squeezenet function.

The model is compiled with the Adam optimizer and sparse categorical cross-entropy loss.

Training is performed for 10 epochs.

4. Evaluation
The model is evaluated on the test set to compute accuracy, ROC-AUC, TPR, and FPR.

Challenges
Due to the large size of the model and dataset, running the code on Google Colab was not feasible. As a result, the model will be trained and evaluated in the next branch using a more powerful environment.

How to Run the Code
1. Clone the Repository
bash
Copy
git clone https://github.com/your-username/electronic-components-classification.git
cd electronic-components-classification
2. Install Dependencies
Install the required Python packages:

bash
Copy
pip install tensorflow numpy scikit-learn pillow
3. Download the Dataset
Download the Basic Electronic Components Dataset from Kaggle:
Basic Electronic Components Dataset

Extract the dataset and place it in the data/ folder.

4. Run the Training Script
bash
Copy
python src/train_model.py
5. Evaluate the Model
After training, the model will be evaluated on the test set, and the results will be printed.

Dependencies
Python 3.7+

TensorFlow 2.x

NumPy

scikit-learn

Pillow (PIL)
