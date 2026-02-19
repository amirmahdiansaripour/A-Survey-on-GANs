# A-Survey-on-GANs
A survey study on the theory and implementation of GAN models (inclduing Cycle-GAN, WGAN, and Style GAN).

### Cycle-GAN:
First introduced in the paper ([Unpaired Image-to-Image Translation Using Cycle-Consistent Adversarial Networks](https://ieeexplore.ieee.org/document/8237506)), this architecture is in fact contained of two sub-GANs: One for image from domain X and one for domain Y.

![img01](./images/cycle_GAN_1.JPG)

In the above capture, ($D_X$, $G$) and ($D_Y$, $F$) make up the first and second GANs, respectively. The goal is to transform a sample from domain X (for example, black and white images) to domain Y (RGB images) and vice versa.