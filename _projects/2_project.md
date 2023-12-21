---
layout: page
title: Magic Hand
description: Meeting assistance that turns intuitive gesture into mouse input.
img: assets/img/Magic Hand/cover.png
importance: 1
category: competition
giscus_comments: truec
---

### Abstraction
We developed a meeting assistant tool that enables the presenter to control the cursor with intuitive arm movement. We implement the functionality of content highlighting and laser pointer manipulation. Besides, we developed an auxiliary cube that enhanced the interaction between participants.
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Magic Hand/cover.png" title="Components" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1. Components of our projects.
</div>

### Details & Links
This is the [link](https://drive.google.com/file/d/148pxIvPggFz4gTC4N_tG4Op8Y3vyrr4Z/view?usp=drive_link) for a demonstration of several functions. We used YOLO v5 to capture body position, shown in Fig. 2, and got the depth map from the Realsense installed on the projector, shown in Fig. 3. 
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Magic Hand/body_pose.png" title="body pose" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 2. The body pose is captured by the YOLO v5 model.
</div>
<div class="row justify-content-sm-center">
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Magic Hand/depth_map.png" title="depth map" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-7 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Magic Hand/depth_map_test.png" title="depth map test" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 3. The depth map is captured by the realsens install on the projector. Left: Schematic figure. Right: raw captured depth map.
</div>
We apply several filters for output stability, like the moving average filter. Besides, we expand the controlling region from the points captured by the YOLO model to the area of the forearm.
As for the cube, we use IMU and vibrating modules to fulfill interactive tasks, like picking a participant by enabling the vibrating motor or anonymous voting by putting different faces down. Shown in Fig. 4.
<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Magic Hand/cube_function.png" title="Cube's function" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Magic Hand/cube_real.png" title="Cube in hand" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 4. Functions of the cube.
</div>
We use the NXP MCU board, which embedded large touch screen, serves as the control panel of changing pointer's function and sending tasks to cubes. Shown in Fig. 5.
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Magic Hand/NXP_board.png" title="NXP board's function" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
   Fig. 5. Functions of the NXP board.
</div>
