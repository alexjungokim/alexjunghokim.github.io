---
layout: page
title: EMG Feature Extraction and Classification
description: Time-domain feature extraction, signal preprocessing, and ML pattern recognition methods for EMG-based gesture classification.
importance: 2
category: research
---

## EMG Features
EMG Features extracted from three domains - time domain (TD), frequency domain (FD), and time-frequency domain (TFD).

Response time of gesture recognition needs to be short/fast to be perceived as real-time. Using time domain features requires no additional processing and reduces total response time.

### Time-domain Features:
- Root Mean Square
- Variance
- Mean Absolute Value
- Slope Sign Change
- Zero Crossing
- Waveform Length

### Classification Performance
SVM, KNN, ANN, CNN, PNN classification models have shown at least 90% accuracy in classifying four-ten hand/finger gestures.

## EMG Signal Preprocessing
EMG signals can get noise from movement artifacts or electrical interference. Filtering techniques include:
- Wavelet analysis / wavelet de-noising
- Higher order statistics
- Empirical mode decomposition
- ANN-based denoising
- Independent component analysis

## ML Pattern Recognition Methods
- **SVM:** Hyperplane-based classification, shown improved accuracy for knee angles and finger movements
- **ANN:** Used for recognizing hand gestures
- **KNN:** Groups data points by majority class of closest neighbors
- **Random Forest:** Ensemble of decision trees for noise resistance
- **HMM:** Temporal pattern recognition in sequences of muscle activations
- **CNN:** Feature extraction from time-frequency representations
- **LSTM:** Temporal pattern analysis (RNN variant)
- **ELM:** Single hidden layer feedforward network with random weights
- **LDA:** Linear feature combination for class separation
