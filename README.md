🧫 Fungal Image Classification using VGG19 (Transfer Learning)

Deep learning–based fungal species recognition using transfer learning with VGG19, enhanced regularization, and robust evaluation metrics.

📘 Overview

This project implements a Convolutional Neural Network (CNN) model based on VGG19 for classifying microscopic fungal images.
It leverages transfer learning from ImageNet and introduces several improvements to boost generalization, stability, and interpretability.

🧠 Model Architecture

Backbone: Pre-trained VGG19 (include_top=False)

Head:

GlobalAveragePooling2D

Dropout

Dense(512, ReLU, L2 regularization)

Dropout

Dense(num_classes, Softmax)

Regularization:

Dropout, L2 Weight Decay, and Label Smoothing (0.1)

Optimizer: Adam (lr=1e-3 for head, 1e-5 during fine-tuning)

Loss: Categorical Cross-Entropy (with label smoothing)

📊 Dataset

Source: Microscopic Fungi Image - DeFungi Dataset (Kaggle)

Classes (5):

Candida albicans

Aspergillus niger

Trichophyton rubrum

Trichophyton mentagrophytes

Epidermophyton floccosum

Preprocessing:

Resize to 224×224

Normalize pixel values [0,1]

Data augmentation (rotation, flip, zoom)

🚀 Training Configuration
Parameter	Value
Batch size	32
Epochs	40
Learning Rate	1e-3 → 1e-5 (fine-tuning)
Optimizer	Adam
Framework	TensorFlow / Keras
Augmentation	In-model (GPU-accelerated)
📈 Results
Metric	Score
Test Accuracy	70.29%
Macro F1	70.67%
ROC AUC	0.932

Highlights:

Overfitting reduced using GAP + Dropout + L2 + Label smoothing

Stable validation curve post LR scheduling

ROC and confusion matrix reveal class-specific weaknesses

🔍 Visualizations

📉 Training curves (Accuracy & Loss)

📊 Confusion Matrix

🧩 ROC Curves per class

🔥 (Optional) Grad-CAM for interpretability
