---
title: "ECU Application Software Development"
excerpt: "<br/><img src='/images/bms_800x500.jpg'>"
collection: portfolio
---

## General Information

**Start Date**: June 2022

**Duration**:  approximately 2.5 years

**Location**: Oensingen, Switzerland

**Employer**: INOMO Technologies AG

**Tags**: automotive, ECU, embedded systems, C programming, RTOS, MISRA, static code analysis, HIL testing, CAN bus, sensor integration.

## Project Description

## Background

This project represents the main work I carried out during my time at **INOMO Technologies AG** (formerly known as **Streetscooter Schweiz AG**). I was part of a small team of engineers responsible for developing the application software, written in C, for a new line of **Battery Management Systems (BMS)** used in electric vehicles and energy storage systems.

The BMS is an embedded device that monitors the status of the battery by processing and analyzing data streams from sensors and other **Electronic Control Units (ECUs)** via the **CAN bus** network. The software runs on a multi-core microcontroller architecture based on a **Real-Time Operating System (RTOS)**.

### Development Processes and Tools

The software development workflow followed an agile approach and included the following steps:

* **Sprint Planning**: The workload for the next sprint (typically two weeks) was decided collaboratively by all team members, with tasks and deadlines assigned to each developer. Issue tracking was managed using Atlassian Jira.  
* **Implementation**: Features were implemented, tested, reviewed (via GitHub), and merged into the main codebase.  
* **Retrospective**: At the end of each sprint, the team held a retrospective meeting to assess progress toward the sprint goals and to adjust plans as needed.  

To ensure compliance with modern automotive standards, the software adhered to the rules defined by [MISRA](https://misra.org.uk/misra-c/). Every new piece of code was statically analyzed using the [QAC Helix](https://www.perforce.com/products/helix-qac) tool before being merged.

Feature testing was conducted using a **Hardware-in-the-Loop (HIL)** setup, in combination with [vTestStudio](https://www.vector.com/it/it/prodotti/products-a-z/software/vteststudio/), an environment for creating automated tests, and [UDE](https://www.st.com/en/partner-products-and-services/ude-universal-debug-engine-multi-core-debugger.html), a debugger for embedded devices such as the BMS.

### Main Contributions

Over the years, I worked on many different software modules. The most important ones include:

* **Insulation Monitoring Device**: Integrated a sensor to detect unwanted discharge currents to the vehicle chassis, and developed a software module that analyzed input signals and performed test routines to ensure safety and fault handling.  
* **Main State Machine**: Contributed to multiple features of the main state machine, which defines how the BMS reacts to specific external signals and conditions.  
* **Power Limits Computation and Monitoring**: Developed a software module to calculate the battery’s power output limits, taking into account variables such as the State of Charge (SoC), temperature, current, cell voltages and derating conditions. The module also included monitoring routines with corresponding fault detection and handling.  
* **CAN Message Processing**: Integrated several new CAN messages into the software, including a complex multiplexed diagnostic message for the energy storage system application.

### Key Learnings

During this project I gained practical experience with the workflow of embedded software development for automotive applications. I practiced implementing and testing code in C on RTOS-based microcontrollers, applied automotive coding standards, and worked with tools for debugging, static analysis, and version control. I also gained experience collaborating in an agile team and contributing to the development and maintenance of large code bases.  
