# Isometric Regularization of Deep Generative Models for Functional Data
Additional experimental results for ICML2024 rebuttal #2803

## 1. 2D Circles 
>radius of circles r=linspace(0.1, 0.5, 20), MLP dimensions=(4, 128, 128, 128, 128, 1), isometric regularization weight=1

- We utilized two sampling schemes for the probability density function p(x; F_z): 1. uniform sampling 2. near-surface sampling 

### Latent Space
<center>
<div class="imgCollage">
<span style="width: 25%"><img src="./images/1/mlp_latent_space.png" height="200"/></span>
<span style="width: 25%"><img src="./images/1/iso_latent_space_0.png" height="200"/> </span>
<span style="width: 25%"><img src="./images/1/iso_latent_space_1.png" height="200"/> </span>
</div>
  <I>Figure 1: <b>(Left)</b> Distorted Latent Space obtained by MLP, <b>(Middle)</b> Latent Space with small curvature obtained by IsoMLP with uniform sampling, and <b>(Right)</b> Latent Space obtained by IsoMLP with near-surface sampling. Blue points are optimized latent codes and green points are linearly interpolated codes between r=0.1 and r=0.5.</I>
</center>
<br>

### Interpolated Results
<center>
<div class="imgCollage">
<span style="width: 31.8%"><img src="./images/1/mlp_interp.png"/></span>
<span style="width: 31.8%"><img src="./images/1/iso_interp_0.png"/> </span>
<span style="width: 31.8%"><img src="./images/1/iso_interp_1.png"/> </span>
</div>
  <I>Figure 2: <b>(Top)</b> Interpolated results obtained by MLP, <b>(Middle)</b> Interpolated results obtained by IsoMLP with uniform sampling, and <b>(Bottom)</b> Interpolated results obtained by IsoMLP with near-surface ampling. We computed MSE(multiplied by 1e4) between gt sdf and sdf samples from 128*128 grid. </I>
</center>
<br>
  
### Average errors

| Model        | Average error           |
| ------------- |:-------------:|
| MLP | 2.2159 |
| IsoMLP (uniform)      | 0.3615      |
| IsoMLP (near-surface) | 0.4310      |

We computed MSE(multiplied by 1e4) between SDF samples from interpolated latent codes and GT SDF.

## 2. 3D Box, Cone, Cylinder
