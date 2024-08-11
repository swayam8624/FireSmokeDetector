# Fire and Smoke Detection Using Convolutional Neural Networks

## Overview

This project aims to build a real-time fire and smoke detection system using a Convolutional Neural Network (CNN) model trained from scratch. The system processes video feeds from multiple RTSP streams concurrently, enabling the detection of fire and smoke in real-time across various locations.

## Dataset

- **Total Images:** 30,000+ images.
- **Categories:** 
  - Fire
  - Smoke
  - Non-Fire
- **Preprocessing:**
  - All images were resized and normalized to a standard format for consistency.
  - The dataset was split into training and validation sets to ensure the model's robustness.

## Model Architecture

A custom CNN was developed to classify images into one of the three categories: fire, smoke, or non-fire. The architecture was designed to be efficient yet powerful enough to accurately detect fire and smoke in real-world scenarios.

### Key Features:
- **Input Layer:** Accepts images of size `(224, 224, 3)`.
- **Convolutional Layers:** Extract features from the input images.
- **Max-Pooling Layers:** Reduce spatial dimensions, enabling the network to focus on the most significant features.
- **Dense Layers:** Fully connected layers to classify the images.
- **Output Layer:** A softmax layer with three output neurons corresponding to fire, smoke, and non-fire classes.

## Training

The model was trained on the processed dataset using TensorFlow/Keras. Various hyperparameters were tuned to optimize performance while maintaining computational efficiency. The training process included:
- **Data Augmentation:** To enhance the diversity of the training data.
- **Early Stopping:** To prevent overfitting by monitoring validation loss.

### Accuracy:
- **Validation Set:** The model achieved an accuracy of **89.9%** on the validation set.
- **Actual Data:** When tested on actual data, the model reached an accuracy of **92.4%**.

## Real-Time Implementation

To achieve real-time detection, we implemented a multi-threaded solution that processes multiple RTSP streams simultaneously. Each video stream is processed in a separate thread, ensuring the system can monitor several locations at once without significant latency.

### RTSP Stream Processing:
- **Threading:** Each RTSP stream is handled by a separate thread, running the `process_rtsp_stream` function.
- **Model Prediction:** The trained CNN model is used to predict the presence of fire or smoke in each frame of the video streams.
- **Scalability:** The system is scalable to handle multiple video streams concurrently, making it suitable for large-scale deployments.

## Results

The CNN model demonstrated strong performance in classifying fire, smoke, and non-fire images. With an accuracy of **89.9%** on the validation set and **92.4%** on actual data, the model has proven effective in real-world scenarios. The multi-threaded real-time implementation effectively detected fire and smoke across multiple video streams, providing timely alerts.

## Conclusion

This project successfully demonstrates the capability of deep learning in enhancing safety measures through real-time fire and smoke detection. With its high accuracy and real-time processing capabilities, the system is a valuable tool for monitoring large areas, potentially preventing disasters by providing early warnings.

