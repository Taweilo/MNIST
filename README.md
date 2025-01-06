# Hand Write Detection Project - MNIST dataset

```
├── Gradio_final.ipynb                            <- Gradio implementation
├── LICENSE                                       <- MIT Lincense
├── MNIST_project_development.ipynb               <- Python code
├── README.md                                     <- SQL code
├── mnist_cnn_model.h5                            <- CNN trained model
├── output_13_0.png                               <- test image

```
## Introduction
This project demonstrates the creation and deployment of a Convolutional Neural Network (CNN) to classify handwritten digits using the MNIST dataset. The project integrates the model with a Gradio interface to provide a user-friendly way to test digit predictions.

## MNIST dataset
The MNIST dataset is a standard benchmark dataset for image classification. It contains:

- Training Data: 60,000 grayscale images of handwritten digits (28x28 pixels) labeled from 0 to 9.
- Test Data: 10,000 grayscale images for evaluation.
Each image is preprocessed by normalizing pixel values to the range [0, 1] and reshaped to include a channel dimension suitable for CNN input. The labels are one-hot encoded for categorical classification.

## CNN model development
The model is implemented using TensorFlow and Keras with the following architecture:

1.  Input Layer: Accepts images of shape (28, 28, 1).
2. Convolutional Layers:
- 32 filters with a kernel size of (3, 3) and ReLU activation.
- 64 filters with a kernel size of (3, 3) and ReLU activation.
3. MaxPooling Layers: Reduces spatial dimensions after each convolution.
4. Flatten Layer: Converts the 2D feature maps into a 1D vector.
5. Dense Layers:
- 128 units with ReLU activation.
- 10 units with softmax activation for classification.
6. Optimizer: Adam.
7. Loss Function: Categorical Crossentropy.

The model is trained on the MNIST dataset for 10 epochs and validated on 20% of the training data. The trained model is saved as mnist_cnn_model.h5.

## Gradio Implementation 
Gradio provides an interactive web-based interface for testing the trained model:
1. Input: Users draw a digit on a sketchpad.
2. Process: The sketch is converted to a grayscale image, resized to 28x28 pixels, normalized, and reshaped to match the model's input format.
The model predicts the digit with the highest probability.
3. Output: The predicted digit is displayed on the interface.
The Gradio app allows easy and quick testing of the CNN model's performance on user-drawn digits.
