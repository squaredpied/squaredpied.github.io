---
layout: page
title: Task-Priority Kinematic Control System for a Mobile Manipulator
description: Hands-On Intervention
img: assets/projects/task_priority/front_page.gif
importance: 3
category: course
---

Collaborator(s): Lisa Paul, Fatima Yousif

([Report](https://drive.google.com/file/d/1MlIEQ87qab83ofVyapZVuY91HgkpM50H/view?usp=sharing))

---

This project describes the design and implementation of a **kinematic control system** for a **differential-drive robot (Kobuki Turtlebot 2)** equipped with a **4 DOF manipulator (uFactory uArm Swift Pro)**. The system utilizes the **Task-Priority Redundancy Resolution Algorithm** to manage the robot's redundant degrees of freedom and to prioritize tasks based on their importance.

The objective of this project is to enable the **Kobuki Turtlebot** and its manipulator to perform various tasks while ensuring that higher-priority tasks are executed first. The system focuses on managing multiple tasks efficiently in a simulated environment, with potential for real-world applications in autonomous robotics. The implementation was done using the **Robot Operating System (ROS)** and validated within the **Stonefish simulator** to test control strategies and task execution.

# Methodology

The project followed several key steps in implementation:

- **Kinematic Modelling**: Developed a kinematic model for both the **Kobuki Turtlebot 2** and the **uFactory uArm Swift Pro**, enabling precise motion control and task execution.
- **Task-Priority Redundancy Resolution**: Applied the **task-priority redundancy resolution** algorithm to prioritize tasks effectively and manage the robot’s redundant degrees of freedom. Higher-priority tasks were executed first while still managing lower-priority ones.
- **Behavior Trees**: Implemented **behavior trees** to manage task complexity, ensuring smooth task transitions and better system control. Behavior trees systematically handle multiple tasks while maintaining the overall robustness of the system.
- **ROS and Stonefish Simulation**: Leveraged the **ROS framework** to implement the control algorithms and used the **Stonefish simulator** for testing and validation of the system. The simulator provided a robust environment to test various task scenarios before transitioning to potential real-world applications.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/projects/task_priority/control_sys.png" title="System Architecture of the Kinematic Control for Mobile Manipulator" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    System architecture of the kinematic control system for the mobile manipulator.
</div>

# Results

The system was rigorously tested in the **Stonefish simulator**, where the **Kobuki Turtlebot 2** and **uFactory uArm Swift Pro** successfully executed a variety of tasks. The **task-priority redundancy resolution algorithm** ensured that the most important tasks were always given precedence, while the use of **behavior trees** effectively managed the complexity of the task transitions.

The video below showcases the system in action, demonstrating the implementation of the **kinematic control system** using the **task-priority redundancy resolution algorithm** for the mobile manipulator.

<div style="text-align: center;">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/W0Ts6vgpDLE?si=rKfMl3aqbzGdKFP2" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

The simulation results, supported by the demonstration video, highlight the effectiveness of the **task-priority redundancy resolution algorithm** in managing the robot's control system, offering a flexible and scalable solution for mobile manipulator tasks.
