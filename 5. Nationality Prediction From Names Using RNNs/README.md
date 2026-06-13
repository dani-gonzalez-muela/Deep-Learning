# Name-to-Nationality Prediction using Custom RNNs

## Project Overview
This project predicts the nationality of a person based on their name using custom recurrent neural networks (RNNs). Techniques such as padding, class weighting, and F1-score evaluation are employed to handle imbalanced data and improve model performance.

## Objective
Predict the nationality of a person given the sequence of characters in their name.

## Dataset and Preprocessing
- **Dataset:** ~44,500 names from 41 countries (from nam_dict.txt)  
- **Imbalance:** Highly imbalanced (e.g., China, USA, Italy have many more names than others)  
- **Character Set:** 57 unique characters (letters, diacritics, special characters)  
- **Encoding:** Names lowercased and converted to one-hot vectors  
- **Padding:** Short names left-padded to max length of 22 characters for batch processing  
- **Data Split:** Train 70%, Validation 15%, Test 15%  

## Model Architecture
- **Custom single-layer RNN** (PyTorch nn.RNN)  
- **Input size:** 57 (characters)  
- **Hidden size:** Tunable  
- **Output size:** 41 (countries)  
- **Mechanism:** Hidden state updated per character, final hidden state passed to fully connected layer → LogSoftmax  
- **Equations:**  
  - \( h_t = \tanh(W_h x_t + U_h h_{t-1} + b_h) \)  
  - \( y_t = \text{logSoftmax}(W_y h_t + b_y) \)  

## Training Setup
- **Loss Function:** Negative Log-Likelihood (NLLLoss)  
- **Class Weighting:** Inverse-frequency weighting to address imbalance  
- **Optimizer:** Adam  
- **Gradient Clipping:** Norm clipped to 2 to prevent exploding gradients  
- **Metrics:** F1-score (macro) in addition to accuracy for better evaluation  

## Training Process
- Batch forward propagation with hidden states initialized to zeros  
- Validation metrics computed periodically (F1-score, precision, recall, loss)  
- Real-time monitoring of training and validation curves using matplotlib  
- **Results:** Model learned meaningful character-to-country patterns; minority classes remain harder to predict due to imbalance  

## Key Insights
- Padding enabled efficient batch training  
- Class weighting essential to avoid bias toward majority classes  
- F1-score provides a clearer picture of model quality than raw accuracy  
