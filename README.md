Project Summary
This repository contains a set of Python scripts designed for evaluating and comparing the performance of different deep learning models on a dataset of images. The code includes functionalities for preprocessing images, generating predictions, and summarizing the results through metrics and visualizations.

Table of Contents
Features
Requirements
Setup
Usage
Code Overview

Features
Image Preprocessing: Resize and preprocess images for model input.
Model Prediction: Generate predictions from multiple models.
Result Summary: Calculate and display metrics such as correct and incorrect predictions.
Visualization: Plot bar charts to compare correct vs. incorrect predictions for each model.

Requirements
Ensure you have the following Python packages installed:

numpy
pandas
matplotlib
scikit-learn
tensorflow (or keras if using TensorFlow backend)
You can install the required packages using pip:



Ensure that your models (model_vgg16, model_resnet50, model) and preprocessing functions (vgg16_preprocess_input, resnet_preprocess_input) are correctly defined and imported in your script.
Load your test images (X_test) and test labels (y_test), and make sure they are in the correct format.
Usage
Define Target Size and Preprocessing Functions:

Set the target size for your images and define preprocessing functions for each model.


target_size = (64, 64)

preprocess_functions = [
    vgg16_preprocess_input,
    resnet_preprocess_input,
    vgg16_preprocess_input
]
Specify Your Models and Their Names:

Define a list of your models and their corresponding names.


models = [model_vgg16, model_resnet50, model]
model_names = ['VGG16', 'ResNet50', 'Custom CNN']
Summarize Predictions:

Call the summarize_predictions function to evaluate and visualize your models' performance.



summarize_predictions(models, model_names, X_test, y_test, preprocess_functions, lb.classes_, target_size)
Code Overview
get_predictions_and_labels Function: Processes test images, makes predictions with the given model, and returns predicted labels.
summarize_predictions Function: Evaluates each model’s predictions, calculates confusion matrices, and summarizes results. Outputs the summary to an Excel file and generates a bar chart of correct vs. incorrect predictions.
