# **Faster SqueezeNet Architecture**

This repository contains the implementation of an electronic component recognition algorithm based on a custom Faster SqueezeNet deep learning model. The project aims to classify electronic components (such as capacitors, resistors, inductors, transistors, and ICs) with high accuracy and low computational complexity.

The work is inspired by the research paper:
"An Electronic Component Recognition Algorithm Based on Deep Learning with a Faster SqueezeNet"
by Yuanyuan Xu, Genke Yang, Jiliang Luo, and Jianan He, published in Mathematical Problems in Engineering, 2020.
Link to the paper'

## **Key Features**  
- **Fire Module**: Combines 1×1 and 3×3 convolutions to reduce the number of parameters.  
- **Residual Connections**: Inspired by ResNet, these connections help address vanishing gradients and degradation.  
- **Dense Connections**: Inspired by DenseNet, these connections enhance feature reuse and improve performance in early layers.  
- **Batch Normalization**: Added to ensure better convergence.  

## **Model Architecture**  
The model consists of:  
- **1 BatchNorm layer**  
- **3 block layers**  
- **4 convolution layers**  
- **1 global average pooling layer**  

---

## **Simulation Process**

### **1. Data Preprocessing**  
- Images are resized to **128×128 pixels**.  
- Invalid images are filtered out using the `is_valid_image` function.  
- Images are normalized to the range **[0, 1]**.  

### **2. Dataset Creation**  
- A TensorFlow dataset is created using a generator function (`create_dataset`).  
- The dataset is split into:  
  - **Training**: 70%  
  - **Validation**: 15%  
  - **Test**: 15%  

### **3. Model Training**  
- The Faster SqueezeNet model is built using the `build_faster_squeezenet` function.  
- The model is compiled with:  
  - **Adam optimizer**  
  - **Sparse categorical cross-entropy loss**  
- Training is performed for **10 epochs**.  

### **4. Evaluation**  
- The model is evaluated on the test set to compute:  
  - **Accuracy**  
  - **ROC-AUC**  
  - **TPR**  
  - **FPR**  

---

## **Challenges**  
Due to the large size of the model and dataset, running the code on Google Colab was not feasible. As a result, the model will be trained and evaluated in the next branch using a more powerful environment.  

---

## **How to Run the Code**

### **1. Clone the Repository**  
```bash
git clone https://github.com/prrmzz/electronic-components-classification.git
cd electronic-components-classification
