# Deepfake Detection System

## Abstract
Deepfakes have emerged as a significant threat in the digital era, where advanced AI models are used to manipulate videos and create highly realistic but entirely synthetic content. This project presents a robust deepfake detection system using a hybrid deep learning architecture combining Convolutional Neural Networks (CNNs) and Long Short-Term Memory (LSTM) networks. The system leverages CNNs to extract spatial features from individual video frames and LSTMs to capture temporal dependencies across frames. By analyzing subtle inconsistencies in spatial and temporal characteristics, the system can effectively distinguish between real and fake videos. The model uses pre-trained VGG16 for spatial feature extraction and an LSTM layer for temporal modelling, ensuring high accuracy with minimal computational overhead. With this project, we aim to contribute to safeguarding digital integrity by providing an efficient, scalable solution to combat video forgeries in real time.

Check out this <a href = "https://github.com/adityapathakk/Deepfake-Detection-System/blob/main/Poster-CapstoneTeam77-ForgeryDetectionSystem.png">poster</a> that provides an overview of our project!

## What are Deepfakes?
Deepfakes refer to videos or images generated using artificial intelligence that manipulate appearances, expressions, or actions of individuals, making them appear authentic. These are typically created using Generative Adversarial Networks (GANs) or similar AI techniques. While deepfakes can have positive applications in entertainment and creativity, they pose serious threats in spreading misinformation, identity theft, and fraud. Detecting deepfakes is challenging because they often blend seamlessly with authentic content, necessitating advanced solutions like the one developed in this project.

## Methodology
<img src = "https://github.com/adityapathakk/Deepfake-Detection-System/blob/main/VideoForgeryDetection-ProposedWorkFlow-blue.png">

The proposed deepfake detection system employs a hybrid deep learning architecture that integrates CNNs and LSTMs to exploit both spatial and temporal features of videos.  
1. **Data Preprocessing**: Videos are converted into sequences of frames, which are resized to a standard dimension of 112x112. If the video has fewer frames than required, it is discarded.  
2. **Spatial Feature Extraction**: A pre-trained Resnext50 model, processes each frame to extract high-level spatial features such as textures, edges, and patterns that are prone to manipulation in deepfakes. The layers that output the classification have been removed, so that these feature maps are sent to the LSTM. 
3. **Temporal Dependency Modeling**: The sequence of spatial embeddings from the CNN is passed into an LSTM layer, which identifies temporal inconsistencies across frames, such as unnatural transitions or erratic facial movements.  
4. **Classification**: The combined spatial and temporal features are refined in dense layers, with dropout applied to prevent overfitting. The final classification layer uses a sigmoid activation function to predict whether a video is REAL or FAKE.  
This system achieves high accuracy by leveraging pre-trained models for efficiency and an end-to-end pipeline that integrates both spatial and temporal analysis.

## Conclusion  
The rise of deepfake technology demands innovative solutions to mitigate its misuse. This project demonstrates the effectiveness of a hybrid CNN-LSTM model for detecting deepfake videos by combining spatial and temporal feature analysis. The system captures subtle manipulations in video content that are often imperceptible to the human eye. By providing a scalable and efficient pipeline, this project aims to assist organizations, researchers, and individuals in combating the adverse effects of deepfakes. Future enhancements could include real-time detection and adaptation to evolving deepfake techniques, further improving the system's robustness and applicability in diverse domains.
