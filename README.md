# Temporal-NR-GANs
This repository contains all the code and materials requires for the ML term paper.


## INSTRUCTIONS
* All of us must compulsarily be thorough with the NR-GAN paper. We will discuss this saturday on the other papers that we must read and split up the tasks. Kamlesh expects equal contribution from all members, which will be explained during the viva which comes later on. So we must work seriously.
* After the Literature Review is done on **Sept 27**, we will focus heavily on implementation.

If you are new to markdown, don't worry it's damn simple-use this link [MARKDOWN reference](https://www.markdownguide.org/basic-syntax/)


## Useful links
* https://www.youtube.com/watch?v=RRTuumxm3CE&list=PLdxQ7SoCLQAMGgQAIAcyRevM8VvygTpCu
* https://www.youtube.com/watch?v=U0R5i8o_d40


---
* [PAPER: Noise Robust GANS](https://openaccess.thecvf.com/content_CVPR_2020/papers/Kaneko_Noise_Robust_Generative_Adversarial_Networks_CVPR_2020_paper.pdf)

Noise robust GANs (NR-GANs) is a architecture proposed by Takuhiro Kaneko & Yatsuya Harada, essentially learn a clean
image generator even when training images are corrupted by noise. These NR-GANs have been shown to solve this problem without having
complete noise information (e.g., the noise distribution type, noise amount, or signal-noise relationship). To achieve this,
the authors introduce a noise generator and train it along with a clean image generator. They introduce propose distribution and transformation constraints that encourage the noise generator to capture only the noise-specific components. They devise two variants of NR-GANs for signal-independent
noise and three variants of NR-GANs for signal-dependent noise.


### TO DO: **Generative adversarial networks (GANs) [21]**

The problems of GANS don't work when the input is Noisy image degradation is unavoidable in real situations. For example, 
* electronic noise is inevitable in digital imaging [60, 1] 
* estimator variance often appears as noise in graphic rendering [83, 72]. 
Therefore, susceptibility to noise is practically undesirable for GANs

**noise robust image generation**
How can we learn a clean image generator even when only noisy images are available
for training?”
* One solution is to apply a denoiser as preprocess. However, a limitation is that the generator performance highly relies on the quality of the denoiser, which is relatively difficult to learn when clean images are not available for training.
* As an alternative, AmbientGAN [5]
was recently proposed, which provides a promising solution
by simulating the noise corruption on the generated images
and learning the discriminator so that it distinguishes a real
noisy image from a simulatively corrupted generated image. This makes it possible to learn a clean image generator
directly from noisy images without relying on a denoiser. However, a key limitation of AmbientGAN is that it
assumes that the noise corruption process is pre-defined.
Therefore, to utilize it, we need to have all information
about the noise, such as the noise distribution type (e.g.,
Gaussian), noise amount (e.g., standard deviation), and
signal-noise relationship

So the authors proposed To deal with this, we propose noise robust GANs (NRGANs), which can achieve noise robust image generation
without having complete noise information

## IDEA
---

---
