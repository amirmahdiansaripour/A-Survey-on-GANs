# A-Survey-on-GANs
A survey study on the theory and implementation of GAN models (inclduing Cycle-GAN, WGAN, and Style GAN).

### Cycle-GAN:
First introduced in the paper ([Unpaired Image-to-Image Translation Using Cycle-Consistent Adversarial Networks](https://ieeexplore.ieee.org/document/8237506)), this architecture is in fact contained of two sub-GANs: One for image from domain X and one for domain Y.

![img01](./images/cycle_GAN_1.JPG)

In the above capture, ($G$, $D_Y$) and ($F$, $D_X$) make up the first and second GANs, respectively. The goal is to transform a sample from domain X (for example, black and white images) to domain Y (RGB images) and vice versa.

In order to do these transitions, we have to take three loss functions into account:

1. Basic and typical loss functions of each sub-module:
$$L_{GAN}(G, D_Y, X, Y) = E_{y \sim p_{data(y)}}[log \space D_Y(y)] + E_{x \sim p_{data(x)}}[log \space (1 - D_Y(G(x)))]$$

$$L_{GAN}(F, D_X, X, Y) = E_{x \sim p_{data(x)}}[log \space D_X(x)] + E_{y \sim p_{data(y)}}[log \space (1 - D_X(F(y)))]$$

2. Cycle Consistency Loss: 
$$L_{cyc}(G, F) = E_{x \sim p_{data(x)}} [|| F(G(x)) - y ||_1 ] + E_{y \sim p_{data(y)}} [|| G(F(y)) - y ||_1 ]$$

Some outputs of my code on the horse2zebra dataset:

![img01](./images/cycle_GAN_2.JPG)
