---
title: "Design and Development of a Physical Motion Simulator for Sensor Calibration"
excerpt: "<br/><img src='/images/final_setup.png'>"
collection: portfolio
---

## General Information

**Start Date**: October 2017

**Duration**: 7 months

**Location**: Zürich, Switzerland

**Employer**: [Multi Scale Robotics Lab (MSRL)](https://msrl.ethz.ch/)

**Supervision**: Dr. George Chatzipirpiridis, Dr. Alessandro Schär, Prof. Dr. Bradley Nelson

**Tags**: velocity estimation, sensor calibration, physical testbench, mechanical design, Arduino programming, controller design

## Project Description

### Background

This project represented the final step of my Bachelor studies at **ETH Zürich** and was carried out in collaboration with **Magnes AG**, a spin-off of the Multi-Scale Robotics Lab (MSRL). The company specialized in performance monitoring systems for cycling and, at the time, was developing the **STYX Powermeter**—a device mounted directly on the pedal and equipped with both an IMU and a 3D force sensor.

A key challenge for accurate power measurement was the estimation of the **pedal velocity in the pedal frame**, required both for power computation and for calibration of the powermeter. While strapdown integration algorithms were considered as a possible solution, their well-known issue with **integration drift** made them impractical for reliable use.  

As an alternative, a more practical approach was chosen: **building a physical testbench** capable of simulating the pedal–crank motion and collecting high-quality calibration data.  

### Mechanical Design

The first task was to define the mechanical design of the system. A central challenge was to prevent the twisting of the pedal motor wiring as the crank shaft rotated. Two possible solutions were considered (see images below):

1. Using a **slip ring** to decouple the motion of the two cable ends.
2. Employing a **hollow shaft motor** for the crank motion with a timing belt attached to the main shaft. 

Design 1             |  Design 2  
:-------------------------:|:-------------------------:  
![Design 1](/images/design_1.png) | ![Design 2](/images/design_2.png)

After careful evaluation, the slip ring solution was selected due to its elegance, cost-effectiveness, and practicality. The sytem components were designed using **Siemens NX CAD**, cut with a highly pressurized water jet, and the setup was subsequently assembled. Additional features included a casing for the electronic components and a **physical user interface** to tune system parameters in real time. The full system setup is shown below.

![Final Setup](/images/final_setup.png)

### Control Implementation

The system was coordinated by an **Arduino Mega**, which handled communication with the motors and interface. Two digital **PID controllers** were implemented:

- The **main shaft motor** was controlled in angular velocity, following prescribed velocity profiles.  
- The **pedal motor** was controlled in position, executing a trajectory mimicking a cyclist’s pedaling motion.  

To improve robustness, **signal filtering techniques** were applied to manage noise in the motor signals. Furthermore, the physical user interface allowed real-time tuning of controller gains, making the system flexible for experimentation.  

### Outcome and Key Learnings

With the system operational, it became possible to map IMU measurements to pedal velocities that could be used to calibrate the powermeter. Although the actual data collection and calibration process was carried out by another student as a continuation of this project, my contribution established the mechanical and control foundation for the testbench.  
  
This project offered valuable experience in the areas of mechanical design, embedded control programming, and experimental robotics hardware, and provided a holistic exposure to building a system from concept through to assembly, programming, and operation.
