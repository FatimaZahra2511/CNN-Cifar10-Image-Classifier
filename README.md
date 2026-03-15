# CNN Image Classification on CIFAR-10

![Python](https://img.shields.io/badge/Python-3.9-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-DeepLearning-orange)
![Dataset](https://img.shields.io/badge/Dataset-CIFAR10-green)


## Overview

This project implements a **Convolutional Neural Network (CNN)** for image classification using the **CIFAR-10 dataset**. The goal is to train a deep learning model capable of recognizing objects in images across ten different categories.

The project explores how different **hyperparameters and architectural choices** affect the performance of a CNN model. Multiple experiments were conducted by varying learning rate, dropout rate, batch size, and the number of convolutional filters.

---

## Dataset

The model is trained on the **CIFAR-10 dataset**, a widely used benchmark dataset for image classification tasks.

Dataset characteristics:

- **60,000 color images**
- **32 × 32 pixel resolution**
- **10 object categories**

Classes in the dataset:
- airplane
- automobile
- bird
- cat
- deer
- dog
- frog
- horse
- ship
- truck

The dataset is loaded directly using TensorFlow:
```python
tf.keras.datasets.cifar10.load_data()

---

## Model Architecture

The project implements a **Convolutional Neural Network (CNN)** using **TensorFlow/Keras** to classify images from the CIFAR-10 dataset.

The network is designed to progressively extract spatial features from images through convolutional layers, reduce dimensionality using pooling layers, and perform classification using fully connected layers.

### Network Architecture

| Layer | Configuration | Purpose |
|------|---------------|--------|
| Input | 32 × 32 × 3 RGB Image | Input image from CIFAR-10 |
| Conv2D | 32 filters, 3×3 kernel, ReLU | Feature extraction |
| Conv2D | 32 filters, 3×3 kernel, ReLU | Deeper feature learning |
| MaxPooling2D | 2×2 pool size | Spatial dimensionality reduction |
| Dropout | 0.25 | Regularization |
| Conv2D | 64 filters, 3×3 kernel, ReLU | Higher-level feature extraction |
| Conv2D | 64 filters, 3×3 kernel, ReLU | Complex pattern detection |
| MaxPooling2D | 2×2 pool size | Further dimensionality reduction |
| Dropout | 0.25 | Regularization |
| Flatten | — | Convert feature maps to vector |
| Dense | 512 neurons, ReLU | High-level representation learning |
| Dropout | 0.5 | Prevent overfitting |
| Dense | 10 neurons, Softmax | Output classification layer |

### Key Components

- **Convolutional Layers**  
  Extract spatial features such as edges, textures, and shapes from the images.

- **Max Pooling Layers**  
  Reduce spatial dimensions while preserving the most important features.

- **Dropout Layers**  
  Improve generalization by randomly disabling neurons during training.

- **Fully Connected Layers**  
  Combine extracted features to perform final classification across the 10 CIFAR-10 categories.
---

## Training Configuration

The model was trained using the following configuration:

| Parameter | Value |
|-----------|-------|
| Optimizer | Adam |
| Loss Function | Categorical Crossentropy |
| Batch Size | 64 |
| Epochs | 10–20 |
| Dataset | CIFAR-10 |

Pixel values were **normalized to the range [0,1]**, and class labels were **one-hot encoded** to support multi-class classification.

---

## Hyperparameter Experiments

Several experiments were conducted to analyze how different hyperparameters affect the performance of the CNN model.

### Learning Rate

Tested values:
- 1e-5
- 1e-4
- 1e-3
- 1e-2
The learning rate controls how quickly the model updates its weights during training. Different learning rates were tested to balance convergence speed and model stability.

---

### Dropout Rate

Tested values:
0.1
0.2
0.3
0.4
0.5
Dropout was used as a **regularization technique** to reduce overfitting and improve the model's ability to generalize to unseen data.

---

### Batch Size

Tested values:
32
64
128
This experiment analyzed the trade-off between **training stability**, **memory usage**, and **computational efficiency**.

---

### Number of Filters

Tested values:
16
32
64
Increasing the number of convolutional filters allows the network to learn **more complex spatial features** from the input images.

---
## Results

Final model performance:

| Metric | Value |
|------|------|
| Test Accuracy | ~79% |
| Optimizer | Adam |
| Batch Size | 64 |
| Epochs | 15–20 |

The trained CNN demonstrates strong classification performance on the CIFAR-10 dataset.

Training performance was analyzed using:

- Accuracy curves
- Loss curves
- Hyperparameter comparison plots

---

## Confusion Matrix Evaluation

The best-performing model was evaluated using a **confusion matrix** on a subset of test images.

The confusion matrix helps visualize:

- Correct classifications (diagonal values)
- Misclassifications between visually similar classes
- Class-specific model performance

This evaluation provides insights into where the model performs well and where improvements can be made.

---

## Example Model Predictions

The best model was used to classify **10 images from the test dataset**.

Predictions were compared with the ground truth labels and visualized using a confusion matrix.

---

## Technologies Used

- **Python**
- **TensorFlow**
- **Keras**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Scikit-learn**

---

## Running the Project

Run the training script or notebook to reproduce the experiments.

Example:

python train_model.py


or run the Jupyter Notebook / Google Colab notebook included in the repository.





