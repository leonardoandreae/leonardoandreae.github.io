---
title: "Optimization-Based Collision Avoidance for ANYmal"
excerpt: "<br/><img src='/images/anymal_sim.png'>"
collection: portfolio
---

## General Information

**Start Date**: February 2021

**Duration**: 7 months

**Location**: Zürich, Switzerland

**Employer**: [Robotic Systems Lab](https://rsl.ethz.ch/)

**Supervision**: Dr. Farbod Farshidian, Dr. Julian Nubert, Prof. Dr. Marco Hutter

**Tags**: master thesis, ANYmal, legged robotics, collision avoidance, optimal control, MPC, conic optimization, operator splitting, augmented lagrangian, SOCP, ROS, C++ programming.

## Project Description

This project represented my final academic endeavor at ETH Zürich, my Master’s thesis.  

The work focused on improving collision avoidance for robotic systems. Typical approaches rely on **Euclidean Signed Distance Fields (ESDFs)** to compute distances between the robot and surrounding obstacles. While effective in many cases, ESDFs are not differentiable everywhere, which can cause numerical issues and slow convergence in optimization methods that rely on gradient information. The goal of the thesis was to develop an alternative approach to overcome these limitations.  

The target platform was **ANYmal** (see picture below), the famous quadruped robot developed by ANYbotics and the Robotic Systems Lab (RSL).  

![ANYmal](/images/anymal_.png)

---

### Approach

The method proposed in this thesis was based on **Model Predictive Control (MPC)**, formulating a unified approach to trajectory planning and motion control with integrated obstacle avoidance constraints.  
A key insight was to exploit **strong duality**: by dualizing the obstacle avoidance constraints, they could be reformulated in a differentiable form under certain conditions.  
The trade-off, however, was the introduction of a large number of additional decision variables, making the problem more challenging for real-time applications.  

To address this, the problem was decomposed into smaller subproblems using an **Operator Splitting** method related to [ADMM](https://stanford.edu/~boyd/admm.html), combined with the **Augmented Lagrangian** technique. The result was a three-step iterative optimization scheme:  

- **State Input Update (SIU):** a standard optimal control problem, solved using the [OCS2](https://leggedrobotics.github.io/ocs2/) toolbox.  
- **Dual Variable Update (DVU):** a Second-Order Cone Program (SOCP), solvable with a variety of open-source and commercial optimization solvers.  
- **Lagrange Multiplier Update (LMU):** a simple algebraic update step without the need for optimization.  

The **DVU step** was critical, as its solve time had a major impact on real-time feasibility. To evaluate different options, a benchmarking study was conducted, leading to the choice of [SuperSCS](https://github.com/kul-optec/superscs) as the solver.  

---

### Implementation

With the theoretical framework in place, a **real-time iteration scheme** was formulated and implemented.  
This required the development of a **C++ interface** to efficiently map the problem into the solver’s format and extract solutions. ROS packages were then created to integrate **SuperSCS** with **OCS2**, enabling both execution of the algorithm and visualization of simulation results.  

The final implementation was tested in simulation on two systems: a **3D floating mass** model and **ANYmal** itself.  

Floating Mass             |  ANYmal  
:-------------------------:|:-------------------------:  
![3D Floating Mass Simulation](/images/mass_.png) | ![ANYmal Simulation](/images/anymal_sim_.png)  

---

### Outcome

The project demonstrated a promising MPC-based approach to collision-free motion planning, with differentiable obstacle avoidance constraints made feasible through Operator Splitting and Augmented Lagrangian methods.  

The work provided insights into solver performance, algorithm design, and implementation challenges for real-time robotic applications, and contributed to ongoing research on advanced motion planning methods for legged robots like ANYmal.  

