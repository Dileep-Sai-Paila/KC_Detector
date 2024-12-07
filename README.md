# KC_Detector

# KCDetector: Portable Creatinine Level Detection

**KCDetector** is an innovative and affordable diagnostic tool designed to detect creatinine levels using a paper strip and a mobile app. This low-cost, easy-to-use system allows users to analyze their creatinine levels by capturing an image of the test strip, which is then processed using image analysis techniques. The device is tailored for resource-limited settings and aims to improve healthcare accessibility by offering a practical solution for early kidney disease detection.

## Table of Contents
1. [Overview](#overview)
2. [How it Works](#how-it-works)
3. [App Workflow](#app-workflow)
4. [API Endpoints](#api-endpoints)
5. [Frontend Details](#frontend-details)
6. [Backend Details](#backend-details)
7. [installation Details](#installation-details)

---

## Overview

Creatinine is a chemical waste product in the blood that passes through the kidneys. The creatinine test helps doctors assess kidney function. KCDetector simplifies the testing process, providing users with a convenient solution for early kidney disease detection.

## How it Works

1. **Capture Image**: The user captures an image of a paper strip that has been used to test creatinine levels.
2. **Image Processing**: The image is processed through the mobile app to extract meaningful features.
3. **Prediction**: The backend uses a machine learning model to estimate the creatinine concentration based on the processed image.
4. **Result Display**: The predicted concentration is displayed in the app, along with a visual closeup of the test image.

## App Workflow

1. **Select Image**: Users can upload an image from the gallery.
2. **Send for Analysis**: The image is sent to the backend for creatinine level estimation.
3. **Receive Results**: The app displays the predicted creatinine level and comparison metrics for image validation (e.g., color similarity, structural similarity).
4. **View Reference Data**: The app provides reference creatinine ranges (low, normal, high) for user comparison.

## API Endpoints

- **/predict**: Receives an image, processes it, and returns the predicted creatinine level, image similarity, and structural similarity index.
- **/greet**: A simple endpoint for testing the API (returns "Hello World!").

## Frontend Details

- **Flet UI**: The frontend uses the Flet framework to create a responsive user interface.
- **Main Components**:
  - File picker for selecting images from the gallery.
  - Progress bar to show processing status.
  - Result display with creatinine levels and visual comparison.
  - Demo button to run a pre-configured analysis for demonstration.

## Backend Details

- **Flask API**: The backend is a Flask application that handles image processing and machine learning predictions.
- **Models**:
  - A **feature extractor** model (pre-trained) to extract features from images.
  - A **Random Forest** model to predict creatinine levels based on the extracted features.
- **Image Processing**:
  - Converts uploaded images into grayscale, applies thresholding, and computes similarity metrics (color and structural similarity) compared to a reference image.
  - Resizes uploaded images and finds contours to crop the test strip.
- **ML Models**:
  - The feature extractor model is a deep learning model that processes the input image.
  - The Random Forest model predicts the creatinine level from the extracted features.

## Installation Details

- Install the app (.apk file) on your Android device. That's it!
