# Concrete Wall Crack Detection using Computer Vision

## Overview
This project develops an automated wall crack detection system using Computer Vision techniques[cite: 3]. It aims to address the limitations of manual visual inspections, mitigate safety risks associated with inspecting high-rise buildings, and improve the efficiency of large-scale structural monitoring.

## Technical Architecture
* **Feature Extraction:** Histogram of Oriented Gradients (HOG) was selected over Local Binary Pattern (LBP)[cite: 3]. HOG demonstrated superior capability in detecting the sharp gradient changes and edge orientations that are characteristic of wall cracks[cite: 3]. The optimal HOG parameter was established at a 16x16 cell size.
* **Classification Model:** Random Forest Classifier was chosen as the primary model after benchmarking against SGD, SVM, KNN, Logistic Regression, and GaussianNB. Random Forest provided the most stable performance and effectively handled the multidimensional features extracted by HOG.
* **Hyperparameter Optimization:** Automated hyperparameter tuning was conducted using Optuna over 100 trials[cite: 3]. The optimal configuration achieved was `n_estimators: 144`, `max_depth: 17`, `min_samples_split: 6`, and `min_samples_leaf: 1`.
* **Deployment:** The inference system is deployed as an interactive web application utilizing Gradio, and it is hosted publicly on Hugging Face Spaces.

## Dataset & Preprocessing
* The initial raw dataset consisted of 530 images, evenly split into 265 positive and 265 negative samples.
* Data augmentation techniques, specifically 90°, 180°, and 270° rotations along with image flipping, were applied.
* This augmentation process successfully expanded the dataset to 2,650 balanced images, providing sufficient variation to optimally train the model.

## Performance & Results
* **Accuracy:** The final model achieved an accuracy of 77%.
* **F1-Score:** The model reached a Macro F1-Score of 0.790 after Optuna hyperparameter tuning, which is a significant improvement from the 0.669 baseline score achieved with SGD.
* **Validation:** 5-Fold Cross Validation and Learning Curves (Recognition Rate vs. Training Size) confirmed strong model stability and generalization, indicating the model learned effectively without overfitting.

## Core Contributions (Ardelle Jody Nathaniel)
* Executed data preprocessing and augmentation pipelines to balance and enrich the dataset.
* Evaluated feature descriptors and selected the HOG extraction logic for structural robustness.
* Benchmarked multiple classification algorithms and established the Random Forest model baseline.
* Engineered the hyperparameter optimization pipeline using Optuna.
* Conducted the final validation phase, including stability analysis, learning curve evaluation, and confusion matrix assessment.

## Team Members
* Antonius Sebastian Gunadi
* Ardelle Jody Nathaniel
* Kenneth Andrew Lukita
* Revel Cahyadi
* Leonard Vanderson Gani