---
layout: page
title: Image Super Resolution Using Generative Adversarial Networks
description: GAN-based Image Super-Resolution for Enhanced Detail Recovery.
img: assets/img/more_results.jpg
importance: 3
category: work
---

This project delves into the realm of Image Super-Resolution (SR), a technique for generating high-resolution (HR) images from their low-resolution (LR) counterparts. This capability is particularly valuable when dealing with blurred or pixelated images, enabling the recovery of lost details and creation of visually superior versions. Our approach leverages the power of Generative Adversarial Networks (GANs), specifically the architecture proposed by [Super Resolution Generative Adversarial Networks (SRGAN)](https://arxiv.org/pdf/1609.04802.pdf).

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/srgan-architecture.png" title="SRGAN Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    SRGAN Architecture
</div>

To enhance this architecture, we incorporate the concept of [Densely Connected Networks (DCNs)](https://arxiv.org/pdf/1608.06993.pdf). DCNs promote information flow throughout the network by connecting each layer's output to subsequent layers. This strategy fosters feature reuse and gradient propagation, potentially leading to improved performance.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/srgan-densenet.png" title="Densely Connected Convolutional Network" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Densely Connected Convolutional Network
</div>

For training and evaluation, we utilize the [DIV2K dataset](https://data.vision.ee.ethz.ch/cvl/DIV2K/), containing a rich collection of high-quality images. To prepare the data, we apply various transformations that augment the training set and enhance modelgeneralizability. Our network is designed to achieve a 4x upscaling factor, effectively quadrupling the resolution of the input LR image.

## Network Architecture and Training Details

[Our model](https://github.com/davidperezcarrasco/SRGAN-for-Image-Super-Resolution) builds upon the core SRGAN architecture, which consists of a Generator and a Discriminator network. The Generator network employs a series of convolutional layers with Parametric ReLU activations, followed by five residual blocks with Batch Normalization. These residual blocks facilitate deeper network architectures and enhance gradient propagation. Subsequently, upscaling blocks with sub-pixel convolutions are utilized to achieve the desired 4x resolution increase. The Discriminator network, responsible for distinguishing between real HR images and the Generator's outputs, leverages strided convolutions and fully-connected layers for image classification.

To further improve the model's performance, we incorporate the principles of Densely Connected Networks (DCNs). We implement Densely Connected Residual Blocks, where each layer receives inputs from all preceding layers, promoting feature reuse and potentially leading to superior results. Additionally, we replace element-wise summation with weighted concatenation, allowing the network to learn the importance of each feature map.

Furthermore, to enhance the Discriminator's ability to discern real from generated images, we leverage transfer learning by incorporating a pre-trained VGG19 network. This pre-trained network extracts high-level features from the input HR images, aiding the Discriminator in making more accurate classifications.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/srgan-architecturevgg.png" title="SRGAN with VGG as Transfer Learning for the Discriminator" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    SRGAN with VGG as Transfer Learning for the Discriminator
</div>

The training process involves optimizing a combination of loss functions. The Content Loss, initially implemented as MSE loss, was ultimately replaced with VGG-based perceptual loss to incorporate higher-level feature information. We also employ the Wasserstein Loss function for the Discriminator, promoting stable training dynamics. Finally, a Perceptual Loss is calculated, combining the Content Loss with the Discriminator's feedback to guide the Generator towards producing realistic and detailed HR images.

## Hyperparameter Tuning and Evaluation

Hyperparameter tuning plays a crucial role in achieving optimal model performance. We experimented with various learning rates, both unique and specific to different network components. The number of training epochs was carefully considered, balancing computational cost with the potential for diminishing returns. Additionally, we explored strategies for regulating the adversarial training process, ensuring a balanced competition between the Generator and Discriminator. Batch size selection was guided by the usage of Batch Normalization or Instance Normalization within the network architecture.

To evaluate the model's effectiveness, we employed two standard image quality metrics: Peak Signal-to-Noise Ratio (PSNR) and Structural Similarity Index (SSIM). These metrics quantify the fidelity between the generated HR image and the ground truth HR image. Our final model, termed Weighted Dense ResNet (WDRN) with VGG SRGAN, achieved a PSNR of 29.23 and SSIM of 0.739 after 50 epochs of training.
