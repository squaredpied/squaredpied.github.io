---
layout: page
title: Online Path Planning on a Turtlebot
description: Hands-On Planning
img: assets/projects/online_path_planning/goal1.gif
importance: 4
category: course
---

Collaborator(s): Mohamed Khaled Othman

---

In this project, we implemented a path planner and a low level controller to autonomously guide a differential drive simulated robot to the goal position specified by the user. **Rapidly-exploring random trees (RRT)** is used for obtaining the path from the start to the goal position. The gridmap that is used for the path planning is obtained from an **octomap server**. All these are achieved using the **ROS** framework.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/projects/online_path_planning/online_planning_architecture.png" title="Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Online Planning Architecture
</div>

# RRT Planner

In order to implement the RRT algorithm, two classes were defined, **tree_node** and **Planner**. The **tree_node** class is used to define the properties of a tree node, such as its position in the grid map and parent node. The **Planner** class contains methods for implementing the RRT algorithm, path generation, and path smoothing.

The RRT algorithm iteratively chooses random positions in space with a $$(1-p)$$ probability and the goal position with $$p$$ probability using the **q_random** method. The position chosen is called _q_rand_. The nearest tree node to _q_rand_ is selected, and the algorithm tries to extend to _q_rand_ from the nearest node by a distance $$\Delta q$$. If there is no obstacle within the extension line, the extended position, called _q_new_, is added to the edges and nodes of the tree. This process continues until the goal node is part of the tree or the maximum number of iterations is reached.

# Demonstrations

Here are demonstrations of the robot reaching various goal positions:

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid path="assets/projects/online_path_planning/goal1.gif" title="Robot going to goal position 1" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Robot going to goal position 1
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid path="assets/projects/online_path_planning/goal2.gif" title="Robot going to goal position 2" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Robot going to goal position 2
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid path="assets/projects/online_path_planning/goal3.gif" title="Robot going to goal position 3" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Robot going to goal position 3
</div>

You can see the robot in action as it plans and moves autonomously toward its goal position in each of the demonstrations above.
