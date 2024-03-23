---
layout: page
title: Generative Adversarial Networks for Image Super-Resolution
description: GAN-based Image Super-Resolution for enhanced detail recovery, achieving  4x upscaling of image resolution while preserving fine details.
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

For training and evaluation, we utilize the [DIV2K dataset](https://data.vision.ee.ethz.ch/cvl/DIV2K/), containing a rich collection of high-quality images. To prepare the data, we apply various transformations that augment the training set and enhance modelgeneralizability. Our network is designed to achieve a 4x upscaling factor, effectively quadrupling the resolution of the input LR image.

### Network Architecture and Training Details

[Our model](https://github.com/davidperezcarrasco/SRGAN-for-Image-Super-Resolution) builds upon the core SRGAN architecture, which consists of a Generator and a Discriminator network. The Generator network employs a series of convolutional layers with Parametric ReLU activations, followed by five residual blocks with Batch Normalization. These residual blocks facilitate deeper network architectures and enhance gradient propagation. Subsequently, upscaling blocks with sub-pixel convolutions are utilized to achieve the desired 4x resolution increase. The Discriminator network, responsible for distinguishing between real HR images and the Generator's outputs, leverages strided convolutions and fully-connected layers for image classification.

To further improve the model's performance, we leverage the principles of [Densely Connected Networks (DCNs)](https://arxiv.org/pdf/1608.06993.pdf). DCNs promote information flow throughout the network by establishing connections between each layer's output and all subsequent layers. This strategy fosters feature reuse and facilitates gradient propagation, potentially leading to superior performance. We implement this concept by employing Densely Connected Residual Blocks. These blocks ensure that each layer receives inputs from all preceding layers, allowing the network to learn a more comprehensive representation of the image features. Additionally, we replace element-wise summation with weighted concatenation. This enables the network to assign varying importance to different feature maps, potentially leading to more effective feature utilization and improved image reconstruction.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/srgan-densenet.png" title="Densely Connected Convolutional Network" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Densely Connected Convolutional Network
</div>

Furthermore, to enhance the Discriminator's ability to discern real from generated images, we leverage transfer learning by incorporating a pre-trained VGG19 network. This pre-trained network extracts high-level features from the input HR images, aiding the Discriminator in making more accurate classifications.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/srgan-vgg19.png" title="VGG-19 is used as Transfer Learning for the Discriminator" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    VGG-19 is used as Transfer Learning for the Discriminator
</div>

The training process involves optimizing a combination of loss functions. The Content Loss, initially implemented as MSE loss, was ultimately replaced with VGG-based perceptual loss to incorporate higher-level feature information. We also employ the Wasserstein Loss function for the Discriminator, promoting stable training dynamics. Finally, a Perceptual Loss is calculated, combining the Content Loss with the Discriminator's feedback to guide the Generator towards producing realistic and detailed HR images.

### Training Performance and Evaluation

Hyperparameter tuning plays a crucial role in achieving optimal model performance. We experimented with various learning rates, both unique and specific to different network components. The number of training epochs was carefully considered, balancing computational cost with the potential for diminishing returns. Additionally, we explored strategies for regulating the adversarial training process, ensuring a balanced competition between the Generator and Discriminator. Batch size selection was guided by the usage of Batch Normalization or Instance Normalization within the network architecture.

**Convergence Analysis**

The SRGAN training exhibits successful convergence, with the generator loss steadily decreasing to below 0.01 after 50 epochs, indicating effective learning to produce high-resolution images. The discriminator loss consistently hovers around -1, which aligns with the expected behavior for Wasserstein GANs where the loss is bounded. While a negative loss might seem unusual, it signifies the discriminator's difficulty in differentiating between the generated high-resolution images and the real data. This reinforces the effectiveness of the training process, as the goal is precisely to generate images that closely resemble real HR examples. Furthermore, the fluctuations observed in the discriminator loss during initial stages are common in GAN training, reflecting the optimization process. In conclusion, the loss patterns provide strong evidence that the SRGAN is functioning well and achieving its objective of generating high-quality, realistic HR images.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/srgan-discloss.png" title="Discriminator Loss" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/srgan-genloss.png" title="Generator Loss" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Discriminator and Generator Losses
</div>

To evaluate the model's effectiveness, we employed two standard image quality metrics: Peak Signal-to-Noise Ratio (PSNR) and Structural Similarity Index (SSIM). These metrics quantify the fidelity between the generated HR image and the ground truth HR image. Our final model, termed Weighted Dense ResNet (WDRN) with VGG SRGAN, achieved a PSNR of 29.23 and SSIM of 0.739 after 50 epochs of training.

### Results

The following images showcase the performance of our SRGAN model. We present comparisons showcasing the original low-resolution (LR) images alongside the corresponding high-resolution (HR) images generated by the model.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/more_results.jpg" title="LR vs SR Image Comparison" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Original Low Resolution Images compared with the Super Resolution Generated Images by our Model
</div>

To further assess our model's performance, we directly compare its generated images with those produced by the [baseline SRGAN architecture](https://arxiv.org/pdf/1609.04802.pdf). We will present three images side-by-side: the original low-resolution input, the HR image generated by the baseline SRGAN (which might exhibit some blur), and the HR image created by our model, which showcases superior quality and smoother details.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/srgan-low.png" title="Original Low Resolution Image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/srgan-benchmark-blur2.png" title="Super Resolution Generated Image from Baseline SRGAN Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/srgan-sr" title="Super Resolution Generated Image from our SRGAN Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    From left to right:  Original Low-Resolution Input, Baseline SRGAN Output (potential blur), Our Model's Output (improved quality and smoothness)
</div>

### References

Arjovsky, M., Chintala, S., & Bottou, L. (2017, July). [Wasserstein generative adversarial networks](https://proceedings.mlr.press/v70/arjovsky17a.html). In International conference on machine learning (pp. 214-223). PMLR.

Chen, X., Wang, X., Zhou, J., Qiao, Y., & Dong, C. (2023). [Activating more pixels in image super-resolution transformer](https://openaccess.thecvf.com/content/CVPR2023/html/Chen_Activating_More_Pixels_in_Image_Super-Resolution_Transformer_CVPR_2023_paper.html). In Proceedings of the IEEE/CVF conference on computer vision and pattern recognition (pp. 22367-22377).

Huang, G., Liu, Z., Van Der Maaten, L., & Weinberger, K. Q. (2017). [Densely connected convolutional networks](https://openaccess.thecvf.com/content_cvpr_2017/html/Huang_Densely_Connected_Convolutional_CVPR_2017_paper.html). In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 4700-4708).

Ledig, C., Theis, L., Huszár, F., Caballero, J., Cunningham, A., Acosta, A., ... & Shi, W. (2017). [Photo-realistic single image super-resolution using a generative adversarial network](https://openaccess.thecvf.com/content_cvpr_2017/html/Ledig_Photo-Realistic_Single_Image_CVPR_2017_paper.html). In Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 4681-4690).
