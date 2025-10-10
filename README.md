# Deep Learning Projects

## Overview
This collection explores deep learning applications, including image classification, generative models, natural language processing, and unsupervised feature mapping. Projects demonstrate convolutional networks, recurrent networks, transformers, self-organizing maps, and diffusion-based text-to-image generation.

## Projects

### 1. Text-to-Image Generation with Diffusion Models
- **Objective:** Generate images from text prompts using diffusion models.
- **Models:** Stable Diffusion, UNet, CLIP-based text encoder.
- **Results:** High-quality image generation; diverse outputs conditioned on text.

### 2. Cats vs Dogs Classification with CNN & Transfer Learning
- **Objective:** Classify cats and dogs using convolutional neural networks.
- **Models:** CNN from scratch; Transfer Learning with VGG16 (frozen & fine-tuned).
- **Results:** CNN validation accuracy ~80%; VGG16 transfer learning ~98% validation accuracy.

### 3. Pokémon Go Classification (Location-Based)
- **Objective:** Predict appearance of three Pokémon species based on latitude and longitude.
- **Models:** Neural networks of varying complexity.
- **Results:** Validation/test accuracy ~73%.

### 4. Name-to-Nationality Prediction with RNN
- **Objective:** Predict nationality from a person’s name character sequence.
- **Models:** Custom RNN with padding and class weighting.
- **Results:** Improved F1-score on imbalanced dataset; model learns meaningful character-country patterns.

### 5. IMDB Movie Sentiment Classification with Transformers
- **Objective:** Classify IMDB movie reviews as positive or negative.
- **Models:** Custom Transformer layers; pre-trained DistilBERT as backbone.
- **Results:** High downstream task performance using transfer learning; attention visualization interpretable.

### 6. Restricted Boltzmann Machine on XOR Dataset
- **Objective:** Train RBM to model XOR 3-bit patterns.
- **Models:** Contrastive Divergence (CD-k) with varying hidden neurons.
- **Results:** Best Kullback-Leibler divergence with 4 hidden neurons; simulated probabilities approximate target distribution.

### 7. Neural Networks from Scratch
- **Objective:** Build and train basic feedforward networks manually.
- **Models:** Fully connected networks with ReLU and Sigmoid activations.
- **Results:** Achieved reasonable accuracy on small datasets (example: ~70–80%).

### 8. Self-Organizing Map (SOM)
- **Objective:** Unsupervised feature mapping and clustering.
- **Models:** 2D SOM with neighborhood functions.
- **Results:** Organized input patterns into topologically meaningful clusters; qualitative visualization used.
