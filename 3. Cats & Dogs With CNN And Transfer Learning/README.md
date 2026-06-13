# Cats vs Dogs Classification using CNNs and VGG16 Transfer Learning

## Project Overview
This project implements convolutional neural networks (CNNs) and transfer learning using VGG16 to classify cats and dogs. Key improvements like data augmentation, normalization, residual blocks, and fine-tuning lead to high performance, achieving up to 98% validation accuracy.

## Dataset and Preprocessing
- **Dataset:** 25K labeled images of cats and dogs  
  - Training set: 80%  
  - Validation set: 20%  
  - External test set used for evaluation  
- **Normalization:** Standardized pixel values (mean, std) to stabilize training  
- **Data Augmentation:** Random flips, rotations, and crops to reduce overfitting  
- **Batching:** Mini-batch size = 64 for memory efficiency and stable convergence  

## Model Design – CNN from Scratch
- **Architecture:** 2 convolutional layers with ReLU activations + fully connected layers  
- **Training:**  
  - Loss: Binary Cross-Entropy (BCE)  
  - Optimizer: Adam  
  - Learning Rate: 0.001  
  - Epochs: 20  
- **Initial Results:**  
  - Training accuracy ~63%, Validation accuracy ~61%  
  - Convergence stable but underfitting observed  

## CNN Improvements
- Added 2 residual blocks for deeper feature extraction  
- Batch normalization before ReLU for stability  
- Max pooling (2x2) after residual blocks  
- **Result:** Validation accuracy improved to ~80%  

## Transfer Learning – VGG16
- **Architecture:** Pretrained VGG16 with custom classifier head (ReLU, BatchNorm, Dropout, Sigmoid)  
- **Motivation:** Pretrained features prevent overfitting and accelerate convergence  
- **Feature Freezing:** Only classifier head trained initially  
- **Results (Frozen Features):**  
  - Training accuracy: ~98%  
  - Validation accuracy: ~98%  
  - Convergence smooth and stable  

## Fine-Tuning
- **Unfreezing:** All convolutional layers trained with small LR = 0.0001  
- **Reasoning:** Gradually adjust pretrained weights without catastrophic forgetting  
- **Results (Fine-Tuned):**  
  - Training accuracy: ~99%  
  - Validation accuracy: ~98%  
  - Slightly higher peak accuracy but less stable than frozen features  

## Key Takeaways
- Transfer learning significantly outperforms models trained from scratch (~80% vs ~98% validation accuracy)  
- Frozen-feature training is fast, stable, and highly effective  
- Fine-tuning slightly improves peak performance at the cost of stability  
- Final model suitable for Kaggle submission and high-accuracy predictions  

