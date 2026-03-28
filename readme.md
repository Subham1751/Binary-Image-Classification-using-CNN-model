# Dog vs Cat Image Classification using CNN

## Project Overview

This project focuses on building a binary image classification model using Deep Learning and Convolutional Neural Networks (CNNs). The objective is to automatically and accurately distinguish between images of dogs and cats.

## Dataset

The model is trained on the popular **Kaggle Dogs vs. Cats Dataset**.

- **Training Set:** 25,000 images (12,500 dogs and 12,500 cats)
- **Test Set:** 12,500 unlabeled images
- **Image Formatting:** All images are resized to `128x128` pixels to maintain uniformity across the network.

## Technologies & Libraries Used

- **Python 3.x**
- **Deep Learning Framework:** TensorFlow & Keras
- **Data Handling:** NumPy, Pandas
- **Visualization:** Matplotlib, Seaborn
- **Machine Learning Utilities:** Scikit-learn (for train-test splitting)
- **Environment:** Jupyter Notebook

## Data Preprocessing & Augmentation

To ensure the model generalizes well and avoids overfitting, several preprocessing steps were applied:

1. **Labeling:** Extracted labels from filenames (`cat = 0`, `dog = 1`).
2. **Normalization:** Rescaled pixel values by a factor of `1/255`.
3. **Data Augmentation:** Applied geometric transformations including rotation, zoom, shear, and horizontal flips.
4. **Data Splitting:** Divided the labeled data into **80% training** and **20% validation** sets.

## Model Architecture

A custom Convolutional Neural Network (CNN) was designed with the following layered architecture:

- **Layer 1:** Conv2D (16 filters) + MaxPooling2D
- **Layer 2:** Conv2D (32 filters) + MaxPooling2D
- **Layer 3:** Conv2D (64 filters) + MaxPooling2D
- **Flatten Layer**
- **Fully Connected Layer:** Dense (512 units, ReLU activation)
- **Output Layer:** Dense (1 unit, Sigmoid activation for binary classification)

**Compilation Details:**

- **Optimizer:** Adam
- **Loss Function:** Binary Crossentropy
- **Evaluation Metric:** Accuracy

## Training Details

- **Epochs:** 50
- **Batch Size:** 32
- **Prediction Threshold:** `Probability > 0.5` → Dog, else Cat.

## Results & Performance

By training the model over **50 epochs** and utilizing image augmentation techniques, the network learned robust feature representations, achieving excellent generalization:

- **Validation Accuracy:** **92%**
- The model successfully minimized validation loss and overcame initial overfitting tendencies observed in earlier epochs.

## Future Work & Improvements

While the current model performs exceptionally well, future enhancements could include:

- Implementing Transfer Learning architectures (e.g., VGG16, ResNet, MobileNetV2) for even higher accuracy.
- Adding Dropout and L2 Regularization layers to further enhance robustness.
- Implementing Model Explainability (e.g., Grad-CAM heatmaps) to visualize what features the CNN focuses on.
- Deploying the trained model as an interactive web or mobile application.

---

_Developed for demonstrating foundational and advanced concepts in Computer Vision and Deep Learning._
