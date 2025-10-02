---
title: "Formalization and Implementation of a Path Planning Algorithm for Autonomous Robot Navigation"
excerpt: "<br/><img src='/images/500x300.png'>"
collection: portfolio
---

## General Information

**Start Date**: March 2020

**Duration**: 4 months

**Location**: Zürich, Switzerland

**Employer**: [Vision for Robotics Lab](https://asl.ethz.ch/v4rl.html)

**Tags**: semester thesis, wheeled autonomous robots, CHOMP, trajectory planning, local path planner, nonlinear optimization, ROS, C++ programming

## Project Description

This project represented my Semester Thesis, a semester-long research work within the Master’s program in Mechanical Engineering at ETH Zürich.  

The work built upon prior developments at the **Vision for Robotics Lab (V4RL)**, where a complete software pipeline for the autonomous navigation of the wheeled mobile robot **SuperMegaBot** (see figure below) had been created. The pipeline integrated modules for object detection, environment mapping, static and dynamic obstacle tracking, global and local trajectory planning, and motion control.  
The focus of my thesis was improving of the **local planner**, which at the time was based on the [CHOMP](https://www.researchgate.net/publication/258141018_CHOMP_Covariant_Hamiltonian_optimization_for_motion_planning) algorithm.  

![SuperMegaBot](/images/supermegabot.png)

---

### Approach

The existing CHOMP-based local planner showed several shortcomings: the state space was over-parameterized with unnecessary dynamic variables, the cost function relied on mathematical workarounds, system constraints were encoded in a scalar summation format that made monitoring individual violations difficult, and the optimization relied on large matrix inversions in a gradient descent scheme. As a result, the optimization was computationally expensive and could only be executed at low frequencies, limiting real-time applicability.  

To address these issues, the optimization procedure was reformulated mathematically from scratch while maintaining a CHOMP-based foundation. The new formulation featured:  

- A reduced state space parametrization.  
- A more efficient and mathematically consistent cost function.  
- A vector-valued representation of system constraints, avoiding the need to impose uniformly accelerated motion between waypoints.  
- Reliance on existing open-source software for constrained nonlinear optimization, thereby eliminating the need for manually implementing gradient descent.  

After benchmarking various commercial and open-source nonlinear optimization solvers, [NLopt](https://nlopt.readthedocs.io/en/latest/) emerged as the best-performing solution for the problem at hand.  

---

### Implementation

The redesigned local planner was implemented as a **ROS package** with a dedicated C++ interface to NLopt. This allowed the planner to perform trajectory optimization efficiently and integrate seamlessly into the existing navigation pipeline.  

Extensive testing was conducted in simulation, with scenarios including both static and dynamic obstacles. These evaluations confirmed the feasibility of the new formulation and demonstrated improved performance compared to the previous approach.  

![SuperMegaBot Simulation](/images/supermegabot_sim.png)

---

### Outcome

The thesis successfully developed and validated an improved local planner for SuperMegaBot. By reformulating the optimization problem and leveraging modern solvers, the work achieved faster computation times, a clearer constraint representation, and greater flexibility in trajectory generation. This contributed to advancing the navigation capabilities of the robot and laid the foundation for further improvements in real-world applications.  
