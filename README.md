# Multimodal Driver Safety Emotion Recognition Using EEG and Facial Features

This work proposes a strong multimodal deep learning model for driver safety that combines EEG signals and facial emotion features. It is intended to track and analyze the cognitive state of a driver by detecting patterns associated with fatigue, distraction, and cognitive load. Combining LSTM and Transformer models for EEG data and CNN-based facial emotion detection facilitates accurate real-time emotion detection. The resulting model marks unsafe driver conditions and raises alerts.

# Overview
Cognitive monitoring is crucial in advanced driver safety systems. Facial expression or camera stream-based traditional methods can be prone to failure during low-light or occluded scenarios. In this project, EEG signals and facial expressions are utilized together to give a comprehensive insight into the mental state of the driver.

# The project employs a multimodal pipeline that:

employs LSTM and Transformer networks to extract temporal and global features from EEG signals.

Leverages a CNN-based facial emotion model pre-trained on actual-world data.

Combines EEG and facial embeddings for ultimate emotion classification and danger detection.

Classifies emotional conditions into safe or hazardous driving states (alert, drowsy, distracted, cognitively overloaded).

Raises warnings when security limits are crossed.

# The EEG data (SEED-IV dataset) consists of:

Records of multiple subjects

Stimuli from four emotion classes (happy, sad, fear, neutral)

EEG signals acquired at 1000Hz

Preprocessed as time-series FFT-based features on multiple channels

# Facial Emotion Dataset:

Employ the dima806/facial_emotions_image_detection model

Gathers emotion probabilities (happy, sad, angry, etc.)

Condenses emotions into distraction/fatigue indicators

# Model Architecture

EEG Branch (LSTM + Transformer)

# LSTM Layers
Capture short-term temporal dynamics in brain signals

# Transformer Block
Uses multi-head self-attention to capture global context
# Contains:

Attention masking

Layer normalization

Feed-forward neural net

Residual connections

# Facial Emotion Branch (CNN)

Pre-trained model to classify facial emotion categories

Outputs are projected onto fatigue/distraction scores

# Fusion Layer

Concatenates EEG and facial feature vectors

Dense layer learns cross-modal representations

# Classification Head

Last softmax layer produces driving state classification

# Labels: Alert, Fatigued, Distracted, Overloaded

Metric	EEG Only	Facial Only	Fused Model

Accuracy	92.10%	89.67%	96.28%

Precision	91.92%	89.34%	96.10%

Recall	91.88%	89.10%	96.22%

F1-Score	91.86%	89.02%	96.13%

Cohen’s Kappa	90.25%	86.88%	94.80%
