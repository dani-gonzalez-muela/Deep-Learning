# Deep Learning Projects

This repository contains a collection of deep learning projects demonstrating applications in computer vision, natural language processing, and structured data modeling. Each project showcases different architectures, techniques, and datasets, highlighting practical implementations and performance evaluation.

## Projects

### 1. Cats vs Dogs Classification
- **Description:** Implements a convolutional neural network (CNN) and transfer learning with VGG16 to classify cat and dog images. Includes data augmentation, normalization, and fine-tuning.  
- **Key Results:** Achieved up to 98% validation accuracy using transfer learning.  

### 2. Pokémon Go Classification
- **Description:** Predicts which Pokémon (Diglett, Seel, Tauros) will appear at a location using latitude and longitude data. Explores neural networks of varying complexity.  
- **Key Results:** ~73% test accuracy capturing geographic patterns; highlights potential improvements from temporal and environmental features.

### 3. Name Nationality Classification
- **Description:** Predicts nationality from a person’s name using custom recurrent neural networks (RNNs). Handles variable-length sequences, class imbalance, and evaluates with F1-score.  
- **Key Results:** Successfully learns country-character patterns; weighted classes essential to handle imbalance.  

### 4. IMDB Movie Sentiment Classification with Transformers
- **Description:** Uses a transformer-based architecture with self-attention and transfer learning from DistilBERT to classify IMDB movie reviews as positive or negative.  
- **Key Results:** Efficient training using frozen pretrained layers; contextual embeddings improve downstream task performance.

### 5. XOR Restricted Boltzmann Machine (RBM)
- **Description:** Trains a Restricted Boltzmann Machine to model 3-bit XOR patterns. Explores hidden layer size effects on Kullback-Leibler divergence and pattern generation.  
- **Key Results:** Larger hidden layers reduce divergence and better approximate the target data distribution.

### 7. Neural Networks from Scratch
- **Description:** Implements feedforward neural networks without using high-level frameworks. Covers forward propagation, backpropagation, gradient descent, and training loops for classification tasks.  
- **Key Results:** Demonstrates fundamental neural network principles and verifies correctness through toy datasets.

### 8. Self-Organizing Map (SOM)
- **Description:** Implements a Self-Organizing Map to cluster and visualize high-dimensional data onto a 2D grid. Explores unsupervised learning and topology-preserving mapping.  
- **Key Results:** Successfully visualizes clusters; shows how SOM captures patterns in high-dimensional input.
