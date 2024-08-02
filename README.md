# Facial Expression Recognition App

This repository contains a machine learning application designed to detect facial expressions using Gradio. Developed in Google Colab, this project uses the CK+ dataset to train models that can recognize various emotions from facial images. The application provides a user-friendly interface for emotion detection through two separate Python notebooks, each employing a distinct model training strategy.

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Notebooks](#notebooks)
  - [Facial Expression Detector](#facial-expression-detector)
  - [Expression Detector Ensemble](#expression-detector-ensemble)
- [Challenges and Solutions](#challenges-and-solutions)
- [Installation and Usage](#installation-and-usage)

## Project Overview

**Situation:** The primary objective of this project was to develop a machine learning application capable of recognizing facial expressions from images. The goal was to build an intuitive and accessible interface using Gradio to showcase the capabilities of machine learning models trained on the CK+ dataset.

**Task:** Develop a Gradio app that leverages deep learning to accurately predict emotions from facial images. This involved preprocessing the CK+ dataset, building and training models, and creating a user interface to interact with the models.

**Action:** Two different approaches were taken to achieve the task:

1. Training a Convolutional Neural Network (CNN) model from scratch.
2. Creating an ensemble model using three pre-trained models from the Keras library.

**Result:** The Gradio app successfully demonstrates emotion detection, providing a foundation for further enhancements and potential real-world applications.

## Dataset

The CK+ (Extended Cohn-Kanade) dataset is used in this project, which consists of labeled facial expressions divided into seven categories, each representing a distinct emotion. These categories are used as output labels for model training.

## Notebooks

### Facial Expression Detector

This notebook involves training a CNN model from scratch using the CK+ dataset. The steps involved are:

- **Data Import and Preprocessing:** Import images, convert them to grayscale, and resize them for uniformity. 
- **Model Building:** Construct the CNN architecture with layers, max pooling, and activation operations.
- **Data Splitting:** Split the data into training and testing sets with an 80/20 ratio.
- **Model Training:** Train the CNN using the preprocessed data.
- **Testing:** Evaluate the model with test images and deploy it via a Gradio app.

### Expression Detector Ensemble

This notebook utilizes an ensemble model approach:

- **Data Preparation:** Upload and extract the CK+ dataset into Google Colab.
- **Ensemble Model Creation:** Combine three pre-trained models from Keras to create an ensemble that averages predictions.
- **Model Loading:** Upload the pre-trained models and execute the code blocks to integrate them.
- **Gradio Interface:** Develop a Gradio app to upload and test images.

## Challenges and Solutions

**Situation:** A major challenge was the ambiguity of predicting emotions with similar facial features, such as anger and fear, which can result in high predictive probabilities for both.

**Task:** To address this, consider integrating contextual information, such as background analysis, to refine emotion predictions.

**Action:** Experiment with different techniques and datasets to enhance model accuracy. Future work may involve additional feature extraction methods or data augmentation to improve differentiation between similar emotions.

**Result:** Initial results indicate that contextual filtering could improve prediction accuracy, providing a direction for future development.

## Installation and Usage

### Prerequisites

- Google Colab
- Gradio
- CK+ dataset and pre-trained models (provided in this repository)

### Running the Notebooks

#### Facial Expression Detector

1. Upload the `ck+model.h5` file to Colab.
2. Install Gradio.
3. Run the Gradio app or console model test at the bottom of the notebook.

#### Expression Detector Ensemble

1. Upload `CK+spl.zip` to Colab and follow the instructions under "Upload and extract CK+ dataset into Colab."
2. Upload all models in the ensemble folder in the "Load the models" section.
3. Execute all code blocks to create the Gradio app.
4. Ensure `class_names` matches the output of the previous code cell.
