---
layout: page
title: Monocular Visual Odometry for an Underwater Vehicle
description: Hands-On Perception
img: assets/projects/mono_vo/intro.gif
importance: 3
category: course
related_publications: false
---

Collaborator(s): Lisa Paul, Fatima Yousif

([Report](https://drive.google.com/file/d/1i3KJji9XgOkrahJ73M-WNIWCNsoDTedC/view?usp=sharing))

---

This project focuses on the implementation of Monocular Visual Odometry (VO) for an Autonomous Underwater Vehicle (AUV), aimed at accurately estimating the vehicle's motion and trajectory. By leveraging images captured from a down-looking camera, the system processes visual data to estimate the AUV’s movement while navigating underwater environments.


# Methodology
The core methodology involves using SIFT feature detection to extract key features from the images and FLANN matching to track these features across consecutive frames, allowing the estimation of the vehicle's relative motion. Given that the down-looking camera views a predominantly planar surface, the system applies homography decomposition to interpret the scene and calculate the AUV’s motion. To enhance accuracy, the system integrates the visual odometry data with sensor inputs through an Extended Kalman Filter (EKF), which fuses visual information with altitude and yaw measurements. This fusion process refines the motion estimates, ensuring more stable and precise trajectory predictions.

The visual odometry system operates through a series of steps:
- **SIFT Feature Detection**: Extracts significant features from underwater images.
- **FLANN Matching**: Matches features between consecutive frames to estimate relative motion.
- **RANSAC**: Ensures robust motion estimation by removing outliers from the feature matches.
- **Homography Decomposition**: Decomposes the homography matrix to estimate rotational and translational movements between frames.
- **Monte Carlo Analysis**: Simulates noise in rotation and translation parameters, which are then used to compute covariances for the EKF update process.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/projects/mono_vo/methodology.png" title="Architecture of the Monocular Visual Odometry Algorithm" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Architecture of the Monocular Visual Odometry algorithm.
</div>

# Results
Below are visual demonstrations of the Monocular VO system in action, showing the estimated motion trajectory compared to the recorded odometry data from the Sparus-II AUV.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/projects/mono_vo/demo.gif" title="Result of Visual Odometry on the Sparus-II AUV" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/projects/mono_vo/demo2.gif" title="Result of Visual Odometry on the Sparus-II AUV" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Results of the visual odometry estimation with EKF
</div>

<!-- # Challenges and Future Work
One major challenge was the **absence of ground truth odometry data**, which made it difficult to fully validate the accuracy of the system. Moving forward, the integration of real-time data processing and comparison with ground truth will be crucial in enhancing the reliability of the system. -->
