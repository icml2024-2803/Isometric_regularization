# Isometric_regularization
Additional experimental results for ICML2024 rebuttal #2803

## 1. 2D Circles 
>radius of circles r=linspace(0.1, 0.5, 20), MLP dimensions=(4, 128, 128, 128, 1), isometric_regularization_weight=1
We trained twenty 2D circles on 2-dimensional latent space.

- We utilized two sampling schemes for the probability density function p(x; F_z): 1. uniform sampling 2. near-surface sampling 

### Latent Space
<center>
<div class="imgCollage">
<span style="width: 25%"><img src="./images/1/mlp_latent_space.png" width="250"/></span>
<span style="width: 25%"><img src="./images/1/iso_latent_space_0.png" width="250"/> </span>
<span style="width: 25%"><img src="./images/1/iso_latent_space_1.png" width="250"/> </span>
</div>
  <I>Figure 1: <b>(Left)</b> Distorted Latent Space obtained by MLP, <b>(Middle)</b> Latent Space with small curvature obtained by IsoMLP with uniform sampling, and <b>(Right)</b> Latent Space obtained by IsoMLP with near-surface sampling. </I>
</center>
<br>

### Interpolated Results
<center>
<div class="imgCollage">
<span style="width: 31.8%"><img src="./images/1/mlp_interp.png"/></span>
<span style="width: 31.8%"><img src="./images/1/iso_interp_0.png"/> </span>
<span style="width: 31.8%"><img src="./images/1/iso_interp_1.png"/> </span>
</div>
  
- Average errors
>We computed MSE(multiplied by 1e4) between SDF samples from interpolated latent codes and GT SDF.

| Model        | Average error           |
| ------------- |:-------------:|
| MLP | 2.2159 |
| IsoMLP (uniform)      | 0.3615      |
| IsoMLP (near-surface) | 0.4310      |

## 2. 3D Box, Cone, Cylinder
