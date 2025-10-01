---
title: "Optimization-Based Collision Avoidance for ANYmal"
excerpt: "<br/><img src='/images/500x300.png'>"
collection: portfolio
---

## General Information

**Start Date**: February 2021

**Duration**: 7 months

**Location**: Zürich, Switzerland

**Employer**: [Robotic Systems Lab](https://rsl.ethz.ch/)

**Tags**: master thesis, ANYmal, legged robotics, collision avoidance, optimal control, MPC, mathematical optimization, C++ programming

## Project Description

This project represents my final academic endeavor at ETH Zürich, my master thesis.

The premise of the work is the following: typical collision avoidance approaches make use of Euclidian Signed Distance Fields (ESDFs) to compute distances between the robot and the surrounding obstacles. While this works well in many cases, ESDFs can cause numerical problems because they are generally not differentiable everywhere, which can lead to slow convergence when using methods relying on gradient information. The algorithm developed in the thesis seeks to find a viable alternative to solve this problem.

The target platform of interest is ANYmal, the famous quadruped robot developed by ANYbotics and RSL, which is represented below.

<p align="center">
  <img src="/images/anymal.png" />
</p>

The approach consists of formulating a holistic, MPC-based method to solve the problem of collision-free trajectory planning and motion control jointly and formulating obstacle avoidance constrainsts exploiting a useful property of strong duality. In fact, by dualizing these constraints, they can be shown to be differentiable.
