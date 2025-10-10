# Pokémon Go Appearance Prediction using Neural Networks

## Project Overview
This project predicts the appearance of three Pokémon species (Diglett, Seel, Tauros) based on latitude and longitude. Neural networks of varying complexity are explored, achieving ~73% accuracy by capturing geographic patterns. Additional environmental and temporal features could further improve predictions.

## Objective
Predict which of the three Pokémon is likely to appear at a given location using only latitude and longitude data.

## Dataset and Preprocessing
- **Dataset:** 296,021 Pokémon sightings with 208 features  
- **Subset:** 3 Pokémon → 2,083 instances (Diglett, Seel, Tauros)  
- **Features used:** Latitude, Longitude, Class  
- **Data split:** Training 55%, Validation 25%, Test 20%  
- **Preprocessing:**  
  - Inputs normalized (mean/std of training set)  
  - Stratified splitting ensures balanced classes  
  - Batching supported for neural network training  

## Data Visualization
- Class distribution roughly balanced (~33% each)  
- Scatter plots show approximate separability:  
  - Tauros → US  
  - Seel → Europe  
  - Diglett → Mexico/southern regions  
- Exact separation difficult due to overlapping regions  

## Neural Network Models
- **Training Loop:** Forward → Cross-Entropy Loss → Backward → Adam optimizer  
- **Architectures:**  
  - **TinyNN:** 1 linear layer → ~55% accuracy; coarse continental patterns  
  - **SimpleNN:** 2 hidden layers → ~73% accuracy; captures geographical patterns  
  - **LargeNN:** 4 layers × 1024 units → overfits, slower convergence  
- **Decision Regions:**  
  - SimpleNN captures intuitive patterns  
  - TinyNN produces coarse predictions  
  - LargeNN overfits; shows need for sufficient data  

## Evaluation
- **Test Accuracy:** ~73%  
- **Confusion Matrix Insights:**  
  - Misclassifications relatively even  
  - Per-class accuracy: Diglett ~77%, Seel ~81%, Tauros ~65% (rarer)  
- **Validation Set:** Used for hyperparameter tuning  
- **Test Set:** Measures generalization  

## Practical Insights
- Focus on US regions to catch all three Pokémon  
- Intermediate network size recommended for fine-grained targeting  
- Overly large models risk memorization rather than generalization  

## Potential Improvements
- Incorporate additional features:  
  - Time of year, day of week, time of day  
  - Terrain type, weather, population density  
- Temporal trends:  
  - Diglett → Saturday nights  
  - Seel → Thursday nights  
  - Tauros → Friday nights  
- Nighttime and terrain type 13 preferred by all three Pokémon  
- Including these features could improve practical predictions and travel planning
