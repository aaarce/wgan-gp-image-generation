# WGAN-GP Image Generation (Fashion-MNIST)

This project explores **stable generative modeling with Wasserstein GANs and Gradient Penalty (WGAN-GP)** using a convolutional generator and critic.  
The goal is to understand how gradient penalties improve training stability and sample quality compared to standard GANs.

## Dataset
- **Fashion-MNIST** (28×28 grayscale images of clothing items)
- Chosen as a more structured and diverse alternative to MNIST digits

## Model
- **Generator**: DCGAN-style convolutional architecture
- **Critic**: Convolutional network with Wasserstein loss (no sigmoid)
- **Training objective**: WGAN with gradient penalty (λ_GP = 10)

## Training Details
- Latent dimension: 128
- Batch size: 128
- Optimizer: Adam (β₁=0.0, β₂=0.9)
- Critic updates per generator step: 5
- Gradient penalty coefficient: 10

## Results
Below are fixed-noise sample grids showing progression over training:

<p float="left">
  <img src="results/samples_epoch_001.png" width="250" />
  <img src="results/samples_epoch_005.png" width="250" />
  <img src="results/samples_epoch_010.png" width="250" />
</p>

## Observations
- Gradient penalty significantly stabilizes training and prevents mode collapse.
- Maintaining a moderate gradient penalty term correlates with sharper and more coherent samples.
- Fixed-noise samples clearly show improvement in structure and coverage over epochs.

## How to Run
```bash
pip install -r requirements.txt
