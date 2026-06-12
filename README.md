# Autonomous-Drone-Landing-Site-Detection-
## Overview

This project focuses on building an intelligent AI-powered landing zone detection system capable of determining whether a drone or aircraft can safely land in a given aerial image. The model classifies terrain into three categories:

Runway → Safe to land
Football Field → Conditionally safe to land
Urban/City Area → Unsafe to land

The system uses Computer Vision and Deep Learning (CNNs) to analyze aerial imagery and generate landing predictions with confidence scores.

The final solution was deployed using a Streamlit web application, enabling real-time image upload and prediction through a user-friendly interface.

## Problem Statement

Autonomous drones and UAVs require intelligent systems to identify safe landing zones in real-time.

Traditional GPS-based systems cannot fully determine:

Surface safety
Urban congestion
Terrain suitability
Emergency landing zones

This project solves the problem by using aerial imagery and deep learning to:

Detect safe landing surfaces
Avoid urban environments
Assist autonomous navigation systems
Features
Image classification using Convolutional Neural Networks (CNN)
Real-time landing safety prediction
Confidence score generation
Heatmap and confusion matrix visualization
Streamlit-based deployment
Support for custom aerial image uploads
Safe/unsafe landing conditional logic
Tech Stack
Programming Language
Python
Libraries & Frameworks
TensorFlow / Keras
OpenCV
NumPy
Matplotlib
Seaborn
Scikit-learn
Streamlit
Deep Learning
Convolutional Neural Networks (CNN)
Deployment
Streamlit Web App
Dataset

The dataset consisted of approximately 6,000 aerial images divided into three classes:

Class	Description
Runway	Airport runways and landing strips
Football Field	Open green fields suitable for emergency landing
City	Urban and densely populated regions
Dataset Sources

Public aerial image datasets were collected from:

Kaggle
Aerial image repositories
Satellite imagery datasets
Project Workflow
### 1. Data Collection

Collected aerial images for:

Runways
Football fields
Cities
### 2. Data Preprocessing

Performed:

Image resizing
Normalization
RGB conversion
Train-test split
One-hot encoding
Example
img = cv2.resize(img, (128,128))
img = img / 255.0
### 3. CNN Model Architecture

The CNN model extracts spatial features from aerial images.

Architecture Includes:
Convolutional Layers
MaxPooling Layers
Dropout Layers
Dense Layers
Softmax Output Layer
Output Classes
0 -> Football Field
1 -> Runway
2 -> City
### 4. Model Training

The model was trained using:

Adam Optimizer
Categorical Crossentropy Loss
Accuracy Metrics
Training Performance
Dataset Size: ~6000 Images
Accuracy Achieved: 96%
### 5. Model Evaluation

Performance evaluation included:

Accuracy
Precision
Recall
F1 Score
Confusion Matrix
Visualization
Heatmaps
Accuracy graphs
Loss graphs
### 6. Landing Decision Logic

Conditional logic was added after prediction.

Example Logic
if predicted_class == "City":
    print("Unsafe to Land")
else:
    print("Safe to Land")
Streamlit Web Application

The trained model was integrated into a Streamlit application.

Features
Upload aerial image
Predict landing safety
Display confidence score
Show landing recommendation
Sample Prediction
Image Type	Prediction	Confidence
Runway	Safe to Land	98%
Football Field	Safe to Land	91%
City	Unsafe to Land	96%
Project Structure
Drone-Landing-Detection/
│
├── dataset/
│   ├── runway/
│   ├── football_field/
│   └── city/
│
├── model/
│   └── landing_model.h5
│
├── app.py
├── train.py
├── predict.py
├── requirements.txt
└── README.md
Installation
Clone Repository
git clone https://github.com/yourusername/drone-landing-detection.git
Install Dependencies
pip install -r requirements.txt
Running the Project
Train the Model
python train.py
Run Prediction
python predict.py
Launch Streamlit App
streamlit run app.py
Future Improvements
Real-time drone camera integration
YOLO-based object detection
Terrain segmentation
Reinforcement learning for autonomous navigation
GPS and sensor fusion
Edge AI deployment on drones
Applications
Autonomous UAV landing systems
Military drone navigation
Emergency landing assistance
Disaster relief drones
Delivery drone systems
Smart aviation systems
Results
Metric	Value
Accuracy	96%
Dataset Size	~6000 Images
Classes	3
Framework	TensorFlow/Keras
Conclusion

This project demonstrates how Computer Vision and Deep Learning can be used to create an intelligent landing zone assessment system for autonomous aerial vehicles.

The model successfully differentiates between:

Safe landing areas
Semi-safe terrains
Unsafe urban environments

The solution achieves high accuracy while remaining lightweight and deployable through a web interface.

Author

Kabir Sharma
B.Tech Computer Science & Engineering
Maharaja Agrasen Institute of Technology (MAIT)

License
This project is open-source and available for educational and research purposes.