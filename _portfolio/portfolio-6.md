---
title: "Parameter Identification and Adaptive Control of an X-Configuration Quadrotor"
excerpt: "<br/><img src='/images/qdrone.png'>"
collection: portfolio
---

## General Information

**Start Date**: February 2019

**Duration**: 3 months

**Location**: Waterloo, Canada

**Employer**: University of Waterloo, Faculty of Engineering

**Supervision**: Prof. Dr. Baris Fidan

**Tags**: quadcopter, system modelling, adaptive control, LQR, Kalman filter, parameter identification, nonlinear dynamics, Matlab, Simulink

## Project Description

### Background

This project was developed as part of the course **“Parameter Identification and Adaptive Control” (ME 780A)**, taught by Prof. Dr. Baris Fidan at the University of Waterloo during my exchange semester. Conducted in collaboration with another student, the project focused on modeling, parameter identification, and adaptive control of a **Quanser QDrone quadcopter** (see picture below).

![Quanser QDrone](/images/qdrone.png)

### Approach

The first step was to derive the **nonlinear equations of motion** of the system from first principles, taking into account its geometry, mass properties, and the effect of gravity. All these parameters were treated as unknowns. In parallel, a **linearized version of the model** was obtained to enable the design of linear controllers under around a defined hovering state.  

With the models established, we proceeded through several stages of development:  

- A **parameter identification scheme** was designed to estimate the unknown system parameters over time. This was achieved by exciting the nonlinear model with a fictitious input and using the system response for identification.  
- Using the linearized model, we implemented an **Adaptive Linear Quadratic Regulator (ALQR)** control law. Since the system was not fully controllable, a **Kalman-Bucy Filter** was incorporated for state estimation.  
- We then combined these approaches into a **nonlinear adaptive control scheme**, integrating the ALQR controller with an **Extended Kalman-Bucy Filter** to account for nonlinear dynamics.  
- Finally, we evaluated the **reference tracking performance** of the controllers in both continuous and discrete-time simulations.

### Implementation

Parameter identification and control structures (see images below) were implemented in Simulink, while the reference tracking tests were performed in Matlab. 

Linear Control Scheme             |  Nonlinear Control Scheme
:-------------------------:|:-------------------------:  
![Linear Control Scheme ](/images/linear_control.png) | ![Nonlinear Control Scheme](/images/nonlinear_control.png)  

### Outcome and Key Learnings

The simulation results demonstrated that the adaptive LQR controller successfully stabilized both the linear and nonlinear systems, while the parameter estimates consistently converged to their true values. Furthermore, our discrete-time non-adaptive LQR implementation showed good reference tracking performance for slow trajectories but exhibited noticeable errors for fast, aggressive maneuvers.  

This project provided valuable insights into adaptive control theory, parameter identification techniques, and their practical application in aerial robotics, while also strengthening my proficiency in Matlab and Simulink for advanced control design and simulation.  
