# Colorization_GAN
Gray-scale Image Colorization using Conditional Generative Adversarial Network.
This is a PyTorch implementation of the DCGAN as described in the paper [Image Colorization using
Generative Adversarial Networks](https://arxiv.org/pdf/1803.05400.pdf)

## Prerequisites
* Python 3.6
* PyTorch
## Method
In a traditional GAN, the input of the generator is randomly generated noise data z. However, this approach is not applicable to the automatic colorization problem due to the nature of its inputs. The generator must be modified to accept grayscale images as inputs rather than noise. This problem was addressed by using a variant of GAN called [conditional generative adversarial networks](https://arxiv.org/abs/1411.1784). Since no noise is introduced, the input of the generator is treated as zero noise with the grayscale input as a prior:
<p align='center'>  
  <img src='https://github.com/kundank78/Colorization_GAN/blob/master/img/con_gan.png' />
</p>
The discriminator gets colored images from both generator and original data along with the grayscale input as the condition and tries to tell which pair contains the true colored image:
<p align='center'>  
  <img src='https://github.com/kundank78/Colorization_GAN/blob/master/img/cgan.png' width='450px' height='368px' />
</p>

## Network Architecture
The architecture of generator is inspired by U-Net: The architecture of the model is symmetric, with n encoding units and n decoding units.
![alt text](https://github.com/kundank78/Colorization_GAN/blob/master/img/unet.png)
For discriminator, we use similar architecture as the baselines contractive path.
## Datasets
We use CIFAR-10 dataset. To train model on fulldataset, Download dataset [here](https://www.cs.toronto.edu/~kriz/cifar-10-python.tar.gz).
## References
1. Image Colorization using GANs. [Paper](https://arxiv.org/pdf/1803.05400.pdf)
2. A TensorFlow Implementation of Image Colorization. [Link](https://github.com/ImagingLab/Colorizing-with-GANs)
