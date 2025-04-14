# Facial Expression Recognition App

The attached notebooks use machine learning to detect 7 facial expressions: happy, anger, contempt, fear, surprise, sadness, disgust. This project uses the CK+ dataset and two approaches- using a single model and multiple models, to categorize the facial expression of any input image. Each approach is in two seperate notebooks in the 'Notebooks' folder. Gradio was used to provide a user-friendly interface for any user to use, in both notebooks.

## Table of Contents
- [Approaches](#approaches)
- [Dataset](#dataset)
- [Notebooks](#notebooks)
  - [Facial Expression Detector](#facial-expression-detector)
  - [Expression Detector Ensemble](#expression-detector-ensemble)
- [Challenges and Solutions](#challenges-and-solutions)
- [Installation and Usage](#installation-and-usage)

## Approaches

1. Training a Convolutional Neural Network (CNN) model from scratch. - *Facial_Expression_Detector.ipynb*
2. Creating an ensemble model (combination of models) by combining the layers of three pre-trained models from the Keras library, and then training it.- - *Expression_Detector_Ensemble.ipynb*

## Dataset

The CK+ dataset (Extended: Cohn-Kanade) is used in this project, which consists of labeled facial expressions divided into seven categories- happy, anger, contempt, fear, surprise, sadness, disgust. These categories are used as output labels for model training.

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

**Challenge::** A major challenge was the ambiguity of predicting emotions with similar facial features, such as anger and fear, which can result in high predictive probabilities for both.

**Solution:** Contextual information, such as image background analysis, can be integrated to refine the emotion predictions.

**Possible implementation of Solution:** Experimenting with different techniques and datasets to enhance model accuracy. Future work may involve additional feature extraction methods or data augmentation to improve differentiation between similar emotions.

**Result:** Initial results indicate that contextual filtering could improve prediction accuracy, providing a direction for future development.

## Installation and Usage

### Prerequisites

- Google Colab (Optional but recommended)
- Gradio (Command to install its dependecies, available in notebook)
- CK+ dataset and pre-trained models (provided in the 'dataset' folder in repo.)

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
