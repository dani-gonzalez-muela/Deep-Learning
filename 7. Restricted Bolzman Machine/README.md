# RBM XOR Project

## Overview
This project trains a **Restricted Boltzmann Machine (RBM)** to model the **XOR dataset** with 3-bit inputs. The RBM learns to generate patterns with probabilities matching the data distribution.

- **Dataset:** 3-bit XOR patterns (8 total).  
- **Target distribution:** 4 patterns with probability 0.25, others 0.  

---

## Method

### Architecture
- **Visible neurons:** 3  
- **Hidden neurons:** M (tested multiple values; 8 expected sufficient)  
- **Training algorithm:** Contrastive Divergence (CD-k)  

### Training Parameters
- Maximum iterations: `vmax = 10000`  
- Gibbs sampling steps: `p0 = 20`  
- Learning rate: `η = 0.005`  

### Procedure
1. Train 20 RBM instances for each M.  
2. Iterate network dynamics 100,000 times per model to generate 3-bit patterns.  
3. Count occurrences of patterns to estimate model probabilities \(P_B\).  
4. Compute **Kullback-Leibler (KL) divergence** versus true data probabilities \(P_\text{data}\).  

---

## Evaluation

**KL Divergence formula:**  

\[
D_{KL} = \sum_{\mu} P_\text{data}(x^{(\mu)}) \log \frac{P_\text{data}(x^{(\mu)})}{P_B(s = x^{(\mu)})}
\]

**Theoretical KL upper bound:**  

\[
D_{KL} \le 
\begin{cases} 
\log(2) \cdot \frac{N - \lfloor \log_2(M+1) \rfloor - (M+1)}{2^{\lfloor \log_2(M+1) \rfloor}} & \text{if } M < 2^{N-1}-1 \\[2mm]
0 & \text{if } M \ge 2^{N-1}-1
\end{cases}
\]

---

## Results
- **Small hidden layers (M=1,2):** Divergences below theoretical bounds but sensitive to parameter choice.  
- **Larger hidden layers (M>2):** Lower, more consistent divergences; easier to fit XOR dataset.  
- **Pattern probabilities:** Approach 0.25 for valid patterns but occasionally generate low-probability “unseen” patterns.  
- **Mean divergence:** Decreases with increasing M; dispersion reduces.  
- **Zero divergence:** Not fully achieved even with more hidden neurons.  

---

## Key Insights
- **Hidden neuron count:** More neurons improve stability and model fit.  
- **Parameter tuning:** Essential for small RBMs to avoid large divergences.  
- **Model behavior:** RBM captures XOR distribution well but may produce rare spurious patterns.  


