# IMDB Movie Sentiment Classification using Transformers

## Project Overview
This project classifies IMDB movie reviews as positive or negative using Transformer architectures and transfer learning. The approach leverages self-attention mechanisms, pre-trained DistilBERT embeddings, and custom classifier layers.

## Objective
Predict the sentiment (positive/negative) of IMDB movie reviews using Transformer-based models.

## Part 1 – Self-Attention Fundamentals
- **Self-Attention Mechanism:** Computes weighted averages across input tokens so each output captures relationships across the sequence.  
- **Implementation:** Efficient matrix operations (torch.bmm) and dot-product attention; softmax normalizes attention scores.  
- **Sequence Length:** Inputs tokenized and padded/truncated to a max length (e.g., 512 for BERT).  

## Part 2 – Transformer Model Architecture
- **Multi-Head Self-Attention:** Projects inputs into Query, Key, and Value spaces for each head; each head captures different dependencies.  
- **Custom PyTorch Module:** Combines attention (SelfAttention class), feed-forward layers, layer normalization, and residual connections (TransformerBlock class).  
- **Positional Embeddings:** Encode sequence order to preserve input structure.  

## Part 3 – Transfer Learning and Dataset
- **Data Loading:** Hugging Face datasets and transformers libraries for IMDB movie reviews.  
- **Backbone Feature Extractor:** Pre-trained DistilBERT provides contextual token embeddings.  
- **Classifier Head:** Custom Transformer layers + linear output map embeddings to class logits (positive/negative).  

## Part 4 – Training and Evaluation Pipeline
- **Frozen Pretrained Layers:** Only custom Transformer and classifier layers are trained; BERT encoder frozen for efficiency.  
- **Training Loop:** Modularized functions for training, validation, and prediction; metrics tracked per epoch (accuracy, loss).  
- **Optimizer & Scheduler:** Adam optimizer with warmup strategy for adaptive learning rates.  

## Part 5 – Model Analysis & Attention Visualization
- **Attention Weight Visualization:** Shows which tokens each head focuses on; interprets model behavior.  
- **Embedding Inspection:** Cosine similarity of learned embeddings highlights semantic clustering and sequence patterns.  

## Part 6 – Key Insights
- **Multi-Head Attention:** Different heads focus on distinct aspects of the input for richer modeling.  
- **Contextual Representation:** Embeddings processed in context allow nuanced language understanding.  
- **Positional Embeddings:** Essential for maintaining sequence information.  
- **Transfer Learning:** Pre-trained models improve downstream task performance with fewer labeled examples.  
