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
