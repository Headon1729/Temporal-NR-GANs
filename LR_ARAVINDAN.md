# Aravindan

In these models, a generator network attempts to map samples from a simple low-dimensional distribution (such as standard
Gaussian) to points in a high-dimensional space that resemble the learned data distribution. At the
same time, a discriminator network attempts to distinguish between real and generated samples.
By setting up a min-max game between them, the two networks are jointly trained. The latent
probability distribution along with the learned generator network define a stochastic procedure that
can produce new samples. The adversarial framework has been shown to be extremely successful
in modeling complex distributions [Berthelot et al. (2017); Vondrick et al. (2016); Pascual et al.
(2017); Wu et al. (2016)], and the priors induced by these models are useful for various applications
[Shrivastava et al. (2016); Ho & Ermon (2016)]

r = real distribution
g = generated distribution
y = observed noisy image
x = clean signal
n = noise

[AMBIENT-GANS](https://www.cs.utexas.edu/~ecprice/papers/ambientgan.pdf)
---
* Learns the underlying distribution from only noisy images.
* They use a noise simulation model assuming prior information about the noise is known and incorporate this the adversial training framework.


our discriminator must distinguish a real
measurement from a simulated measurement of a generated image;

Our method is able to construct good generative models from extremely noisy observations and
even from low dimensional projections with drastic per-sample information loss

We consider the task of learning an implicit generative model given only lossy measurements of samples from the distribution of interest. We show that the true underlying distribution can be provably recovered even in the presence of per-sample
information loss for a class of measurement models

We first consider measurements that are noisy, blurred versions of the desired
images. That is, we consider convolving the original image with a Gaussian kernel and adding
independent Gaussian noise to each pixel (our actual theorem applies to more general kernels and
noise distributions). Because of the noise, this process is not invertible for a single image. However,
we show that the distribution of measured images uniquely determines the distribution of original
images. This implies that a pure Nash equilibrium for the GAN game must find a generative model
that matches the true distribution. 

The idea of operating generators and discriminators on different spaces has been proposed before.
[Neyshabur et al. (2017)] explores an interesting connection of training stability with low dimensional projections of samples. They show that training a generator against an array of discriminators,
each operating on a different low-dimensional projection of the data can improve stability.

Write equations **4(1)**
**GET THE ARCHITECTURE**

---
The primary limitation of AmbientGANS is that it requires that a noise simulation model $Fθ(x)$ is known in prior. [Kaneko,Harada] avoid this by introducing a noise generator and train it along with a clean image generator.

**Eqn 5(2)**
They provide constraints to capture only the noise specific components

## Signal Independent NR-GANS-I
> These models expect 3 assumptions to hold, namely
> 1. The noise n is conditionally pixel-wise independent given the signal x. 
> 2. The noise distribution type (e.g., Gaussian) is priorly known. Note that the noise amount needs not to be known.
> 3. The signal x does not follow the defined noise distribution.

regularize the output distribution of Gn in a pixel-wise manner using a reparameterization trick [40]
 introduce an auxiliary pixel-wise random variable.
__5(3)__

Therefore, the same model can be applied to various noises (e.g., Figure 2(A)–(D), in which
each pixel’s noise follows a Gaussian distribution, while
the noise amount is different in a sample-wise (e.g., (B))
or pixel-wise (e.g., (D)) manner).

> Limitations
> 1. the noise is pixel-wise independent - difficult to apply to a pixel-wise correlated noise
> 2. the noise distribution type is pre-defined - cause difficulty when diverse noises are mixed or the noise distribution type is different from the pre-defined


## Signal Independent NR-GANS-II
Overcomes limitations of __SI-NRGAN-I__
> This model too makes a few assumptions - Both the noise n and signal x must be rotation, channel, color-inverse invariant.
> These assumptions are reasonable when n is a zero-mean signal-independent noise
and x is a natural image.

The noise generator is redefined by taking the initial noise generator and applying a transformation to it. The authors state that it must be applicable to n but not to x.
In practice, we use three transformations: (i) rotation – rotating nˆ by d ∈ {0, 90◦, 180◦, 270◦} randomly,
(ii) channel shuffle – shuffling RGB channels randomly,
and (iii) color inversion – inverting colors randomly in a
channel-wise manner. 


