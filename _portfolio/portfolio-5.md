---
title: "Modelling and Simulation of a Dual Arm Robot Handling an Object"
excerpt: "<br/><img src='/images/500x300.png'>"
collection: portfolio
---

## General Information

**Start Date**: February 2019

**Duration**: 3 months

**Location**: Waterloo, Canada

**Employer**: University of Waterloo, Faculty of Engineering

**Supervision**: Prof. Dr. John McPhee

**Tags**: dual arm robot, multibody dynamics, inverse kinematics, inverse dynamics, controller design, Matlab, MSC ADAMS.

## Project Description

This project was developed as part of the course **“Dynamics of Multibody Systems” (SYDE 652)**, taught by Prof. Dr. John McPhee at the University of Waterloo, which I attended during my exchange semester. It was a collaborative effort carried out by a team of 3 students and focused on the modeling and simulation of a dual-arm robotic system designed to manipulate a heavy object.

The first stage of the project consisted of developing a **mathematical model** of the robot (see figure below). Assuming planar motion, the system was represented as four rigid links with defined geometric and mass properties, while the manipulated object was modeled as a rectangular block with a known mass and dimensions.

![Dual Arm Model](/images/dual_arm_model.png)

Once the structure was defined, we performed a **kinematic analysis** of the system to determine the joint angle trajectories required for a prescribed motion of the load. This step was followed by an **inverse dynamics computation**, where we calculated the joint torques necessary to reproduce the desired motion. To capture the physical interaction more realistically, we incorporated a **sliding contact model** for the load, allowing us to simulate the effects of friction and contact forces.  

Building on this, we implemented a **controller structure** capable of tracking the computed joint torque trajectories, ensuring that the robot could achieve stable and precise motion. All modeling, analysis, and control design steps were carried out in **Matlab**, leveraging its symbolic and numerical toolboxes.  

In the final phase, we validated our model by comparing it against simulations in **MSC ADAMS**, a professional multibody dynamics software widely used in industry. A convergence study was performed to assess the accuracy of our approach, providing confidence in the fidelity of our Matlab-based model.  

This project was a valuable experience in the integration of modeling, dynamics, and control for robotic systems, while also reinforcing the importance of validation through cross-platform comparisons. It further developed my skills in system dynamics, inverse dynamics methods, and simulation-based verification, all within the context of a realistic robotic application.  
