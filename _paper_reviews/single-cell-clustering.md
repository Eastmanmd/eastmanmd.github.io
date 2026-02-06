---
layout: post
title: "Review: Deep Learning in ScRNA-seq"
---
**Paper:** *Author et al., 2024*

**Key Takeaway:** The authors use a Variational Autoencoder (VAE) to reduce dimensionality.
The loss function is defined as:
$$\mathcal{L} = \mathbb{E}_{q(z|x)}[\log p(x|z)] - D_{KL}(q(z|x) || p(z))$$

**My Critique:** The batch effect correction is solid, but the computational overhead is $O(n \cdot log(n))$.
