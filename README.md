#  Image Anomaly Detection: ResNet18 & One-Class SVM

This project implements an anomaly detection pipeline using two distinct methodologies: Deep Learning for feature extraction and Classical Machine Learning .

##  Project Objective
The goal is to identify anomalous images (outliers) by leveraging a model trained on a "normal" dataset. This approach evaluates the effectiveness of high-dimensional feature representations in anomaly detection tasks.

##  Methodologies Used

### 1. Deep Feature Extraction (ResNet18)
* **Backbone**: Uses a pre-trained **ResNet18** model as the feature extractor.
* **Modification**: The final classification layer is replaced with `nn.Identity()`, allowing the model to output a 512-dimensional feature vector for each image.
* **Normalization**: Inputs are resized to 224x224 and normalized to fit the pre-trained model's requirements.

### 2. Anomaly Classification (One-Class SVM)
* **Algorithm**: **One-Class SVM** with an RBF (Radial Basis Function) kernel.
* **Approach**: The model is trained solely on features from the "normal" class to learn a decision boundary.
* **Decision Scoring**: New samples are scored based on their distance from the learned boundary; lower scores indicate potential anomalies.

##  Evaluation & Results
* **Metric**: Performance is measured using the **ROC AUC Score**, which indicates the model's ability to separate normal data from anomalies.
* **Visualization**: The notebook generates **ROC Curves** to visualize the detection performance.
