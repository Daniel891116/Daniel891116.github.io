---
layout: page
title: Out-of-All-Things-One-and-Out-of-One-All-Things
description: This project is inspired by the art work titled "Out of All Things One, and Out of One All Things" created by Petros Vrellis.
img: assets/img/Out-of-All-Things-One-and-Out-of-One-All-Things/preview.jpeg
importance: 2
category: fun
giscus_comments: true
---

### Abstraction
Inspired by the art work by [Petros Vrellis](http://artof01.com/vrellis/), I create my version of "Out of All Things One, and Out of One All Things", which generates three transparent images layer that could be added up to reconstruct the desired image. In this project, I used deep learning network to optimize the pixel value of the three images. Feel free the check out the [repository](https://github.com/Daniel891116/Out-of-All-Things-One-and-Out-of-One-All-Things) of this project.
### Details & Links
This video shows the demonstration of the result of combining generated images.
<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.html path="https://www.youtube.com/embed/C-98xdtjvOo" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Result demonstration.
</div>
To generate those images, we have to pick three images as the guidance of image generation. It is recommanded to pick symmatric and complex images for the generation quality. For example, I pick the following three images to generate the transparent layers, shown in Fig. 1.
<div class="row justify-content-sm-center">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Out-of-All-Things-One-and-Out-of-One-All-Things/base1.jpg" title="image of guidance 1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Out-of-All-Things-One-and-Out-of-One-All-Things/base2.jpg" title="image of guidance 2" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Out-of-All-Things-One-and-Out-of-One-All-Things/base3.jpg" title="image of guidance 3" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1.Guidance for image generation.
</div>
Considering the physical optics and chromatics, we define the desired result $$X$$ and each layer of image $$I_i$$, and we get $$I_1\cdot I_2\cdot I_3 = X_\text{result}$$. To compute the loss, I use Structural Similarity Index measure(SSIM) loss and mean-square(MSE) loss to maximize the pixel difference and the visual difference.
Apart from minimizing the reconstruction loss, the similarity of the generated image should be maintained. Thus, I apply only the SSIM loss to the difference between each guidance image and the corresponding layer. The generated layer is shown in Fig. 2.
<div class="row justify-content-sm-center">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Out-of-All-Things-One-and-Out-of-One-All-Things/layer1.jpg" title="image of layer 1" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Out-of-All-Things-One-and-Out-of-One-All-Things/layer2.jpg" title="image of layer 2" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Out-of-All-Things-One-and-Out-of-One-All-Things/layer3.jpg" title="image of layer 3" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 2.Generated layers.
</div>
The desired image and result are shown is Fig. 3.
<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Out-of-All-Things-One-and-Out-of-One-All-Things/input.png" title="image of final result" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Out-of-All-Things-One-and-Out-of-One-All-Things/result.jpg" title="image of final result" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 3.Final result
</div>