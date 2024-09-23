---
layout: page
title: Autonomous Robot Exploration on a Kobuki Turtlebot2
description: Hands-On Planning
img: assets/projects/explore_turtlebot/test2.gif
importance: 1
category: course
related_publications: false
---

Collaborator(s): Lisa Paul, Fatima Yousif

([Report](https://drive.google.com/file/d/1yGZ9kmJbnZPWXbjMRGob_BECRjHCIesm/view?usp=drive_link))

---

This project presents the development of a **frontier-based exploration system** for autonomous navigation using an **RGB-D camera** mounted on a **Kobuki Turtlebot2**. The objective is to enable the robot to autonomously explore unknown environments by identifying and navigating to frontiers, which are the boundaries between known and unexplored areas. This approach integrates advanced path planning and control algorithms to enhance the efficiency and accuracy of autonomous navigation and mapping.

Our system uses **connected component labeling** to detect and cluster frontiers, selecting exploration targets based on **maximum information gain**. The integration of **RRT* (Rapidly-exploring Random Tree Star)** algorithm with **Dubin's path strategies** allows for efficient path planning while ensuring smooth navigation in open spaces. However, challenges were identified in tight spaces, which were addressed through parameter tuning during testing. Additionally, the robot's velocity and direction were controlled by a hybrid system combining a **PID Controller** for velocity stability and a **Pure Pursuit Controller** for direction management, particularly useful in dynamic environments.

# Methodology
The project employs a combination of path planning and control algorithms:
- **Frontier Detection and Clustering**: The system detects and clusters frontiers using **connected component labeling**, selecting exploration targets based on maximum information gain.
- **RRT* (Rapidly-exploring Random Tree Star)**: Used for efficient path planning, allowing the robot to explore unknown environments while avoiding obstacles.
- **Dubin's Path Strategies**: These were integrated with RRT* to provide smooth, curvature-constrained paths that optimize the robot's navigation in open spaces.

The system was developed in Python and implemented within the **Robot Operating System (ROS)** framework. Preliminary testing and algorithm tuning were carried out in the **Stonefish simulation environment**, with further validation performed in real-world scenarios using the Kobuki Turtlebot.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/projects/explore_turtlebot/system_arch_fe.png" title="System Architecture of Autonomous Robot Exploration" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    System architecture of the autonomous robot exploration system, integrating RRT*, Dubin's paths, and PID control.
</div>

# Results
The results demonstrated the effectiveness of our approach in achieving efficient path planning, exploration coverage, and overall system performance. The integration of **RRT* with Dubin’s paths** facilitated smooth navigation, while the **PID** and **Pure Pursuit** controllers ensured precise control. Both the simulation and real-world tests yielded successful exploration and mapping outcomes, although further refinement in parameter tuning is necessary for constrained environments.

<div style="text-align: center;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/pr2CdoQ64mg?si=KrXT2NUC3Ub2iXRy" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

<!-- # Future Work
Future enhancements could focus on optimizing the performance of **Dubin’s paths** in tight spaces and refining the exploration strategy to handle larger and more complex environments. Further research can also explore real-time adaptive path planning to improve the robot’s ability to navigate in highly dynamic environments. -->
