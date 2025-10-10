## Overview
This project explores generating high-quality images from text prompts using diffusion models, focusing on DDPM, DDIM, and Stable Diffusion. The work investigates fine-tuning, guidance techniques, and the integration of CLIP and BERT embeddings to align generated images with textual descriptions.

## Key Components

### 1. Diffusion Models
- **DDPM**: Progressive denoising to generate images from noise.  
- **DDIM**: More efficient variant, producing similar quality with fewer steps.  
- **Fine-tuning**: Applied to specific datasets (celebrity faces, butterflies) to adapt models.  

### 2. Guidance Techniques
- **Color-based guidance**: Loss function applied to guide generation toward specific visual features.  
- **Classifier-Free Guidance (CFG)**: Adjusts reliance on prompt embeddings to control alignment with text.  
- **Effect of timesteps**: Longer diffusion sequences improve quality up to a point; over-processing can degrade output.  

### 3. CLIP Integration
- Aligns text and image representations in a shared latent space.  
- Optimal guidance strength (~0.8) improves alignment and visual quality.  
- Excessive guidance can destabilize generation, leading to distorted images.  

### 4. Stable Diffusion
- Combines latent diffusion and VAE compression to generate high-resolution images efficiently.  
- UNet with cross-attention layers integrates CLIP embeddings at multiple spatial locations.  
- Latent space compression reduces memory usage while retaining key image details.  

### 5. Latent Space Manipulation
- Encoding and decoding images into latent space allows controlled noise addition.  
- Highlights the importance of precise noise scheduling for high-fidelity image generation.  

### 6. BERT-Guided Generation
- Tested as an alternative to CLIP for text conditioning.  
- Found ineffective due to lack of visual-semantic alignment; generated images are abstract and unstructured.  

### 7. Novel Generations
- Creative prompts demonstrated the model’s flexibility.  
- CLIP guidance enabled more coherent and semantically aligned outputs compared to BERT.  

## Conclusions
- DDIM improves efficiency without sacrificing quality.  
- CLIP embeddings effectively guide images to match prompts; BERT is unsuitable for visual guidance.  
- Stable Diffusion leverages latent space compression and cross-attention to handle high-resolution generation efficiently.  
- Optimal guidance strength, noise scheduling, and latent manipulation are key for high-quality outputs.  
