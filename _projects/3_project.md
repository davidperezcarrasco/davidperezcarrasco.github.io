---
layout: page
title: Image Super Resolution Using Generative Adversarial Networks
description: GAN-based Image Super-Resolution for Enhanced Detail Recovery.
img: assets/img/more_results.jpg
importance: 3
category: work
---

This project delves into the realm of Image Super-Resolution (SR), a technique for generating high-resolution (HR) images from their low-resolution (LR) counterparts. This capability is particularly valuable when dealing with blurred or pixelated images,  enabling the recovery of lost details and creation of visually superior versions.  Our approach leverages the power of Generative Adversarial Networks (GANs), specifically the architecture proposed by [Super Resolution Generative Adversarial Networks (SRGAN)](https://arxiv.org/pdf/1609.04802.pdf).

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

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:
