---
layout: page
title: 3D Reconstruction from Road Marker Feature Points
description: Final project of Computer Vision course
img: assets/img/3D Reconstruction from Road Marker Feature Points/birdview.jpg
importance: 1
category: course
giscus_comments: true
---

### Abstraction
This project performs 3D reconstruction from road marker feature points. Our pipeline consists of several steps, including segmentation, 3D reconstruction, merging views, and refinement.

### Details & Links
This is the [link](https://github.com/Daniel891116/computer_vision_final) to our project’s repository.
We use Meta’s [SAM](https://segment-anything.com/) model to segment the road marker, remove the distracting street background for the segmentation step, and extract the feature points of those detected road markers. 
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/3D Reconstruction from Road Marker Feature Points/feature_points.png" title="feature points" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/3D Reconstruction from Road Marker Feature Points/segmentation.png" title="road mark segmentation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1. The road mark detection after applying SAM model. Left: before. Right: after.
</div>
Next, we reconstructed those feature points by projecting them to the ground of world coordinates, Shown in Fig. 1. I designed the algorithm for merging those overlapped projected feature points by comparing the IoU and the size of each overlapping road marker patch. Thus, we can distinguish whether the overlapping happened to two different road markers. 
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/3D Reconstruction from Road Marker Feature Points/birdview.jpg" title="birdview" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 2. The birdview of projected feature points on real-world coordinates.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/3D Reconstruction from Road Marker Feature Points/overlapped_road_mark.png" title="operlapped road mark" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/3D Reconstruction from Road Marker Feature Points/road_mark.png" title="filtered road mark" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 3. Left: The same road mark projected by different camera. Right: The filtered road mark.
</div>
After getting the surrounded road marker feature points, we use the ICP to calculate the instant location by matching our result with the given feature points of the global environment. Finally, we refine the prediction with a causal filter based on the stability assumption of the car’s movement. For more details, the [link](https://drive.google.com/file/d/10w373dwWkj2aU79Rj4NbaYHNMd77JEEG/view?usp=drive_link) to the project is provided.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/3D Reconstruction from Road Marker Feature Points/raw.png" title="raw trajectory" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/3D Reconstruction from Road Marker Feature Points/raw_2.png" title="raw trajectory" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/3D Reconstruction from Road Marker Feature Points/smoothed.png" title="smoothed trajectory" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/3D Reconstruction from Road Marker Feature Points/smoothed_2.png" title="smoothed trajectory" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 4. Upper left: Raw trajectory of evaluation case 1. Upper Right: Raw trajectory of evaluation case 1.
            Bottom left: Smoothed trajectory of evaluation case 1. Bottom Right: Smoothed trajectory of evaluation case 1.
</div>
