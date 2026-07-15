# Microcontroller-Robot-Path-Planning

An autonomous line-following robot programmed in **HCS12 Assembly** for the **MC9S12DP256 (EEBot)** platform. Developed as the final project for **COE538 – Microprocessor Systems** at Toronto Metropolitan University.

The project integrates optical sensors, motor control, timer interrupts, and an LCD interface into a complete embedded control system capable of following a guide line, correcting its path, and responding to obstacles in real time.

---

## Features

* Line following using five optical sensors
* Finite State Machine (FSM) for navigation
* Automatic left/right alignment and course correction
* Timed turning using Timer Overflow Interrupts
* Front bumper recovery (reverse + turn)
* Rear bumper emergency stop
* Real-time LCD display of robot state and battery voltage
* ADC-based sensor reading and battery monitoring
* Modular assembly routines for easier debugging and maintenance

---

## System Architecture

The software is divided into several independent modules:

* **Initialization** – Configures the ADC, LCD, motor control ports, timer interrupts, and working memory.
* **Sensor Reading** – Continuously samples the five optical sensors to determine the robot's position relative to the guide line.
* **Navigation State Machine** – Controls robot behavior through dedicated states such as Forward, Left/Right Alignment, Left/Right Turn, Reverse Turn, and Stop.
* **Motor Control** – Handles forward, reverse, turning, and stopping using dedicated assembly routines.
* **LCD Interface** – Displays the current navigation state and battery voltage in real time.
* **Timer Interrupt** – Provides accurate timing for turns and other time-dependent operations.

---

## Technologies

* **Language:** HCS12 Assembly Language
* **Platform:** MC9S12DP256 (HCS12)
* **Hardware:** EEBot mobile robot
* **Peripherals:** ADC, LCD, optical sensors, DC motors, bumper switches, timer interrupts

---

## Running the Project

This project was developed for the **MC9S12DP256 (HCS12)** microcontroller using the **EEBot** robotics platform.

To run the program, you will need:

- CodeWarrior IDE for HCS12
- MC9S12DP256 development board / EEBot
- Robot hardware (motors, optical sensors, LCD, and bumper switches)
- The `main.asm` source file

The assembly program can be assembled and loaded onto the HCS12 using CodeWarrior. Once programmed, the robot can be started using the bumper switch and will autonomously follow a guide line while responding to sensor input.

---

## Challenges

Some of the main challenges during development included:

* Calibrating noisy ADC sensor readings for reliable line detection
* Designing and debugging a state-machine-based control system
* Synchronizing LCD communication without affecting robot performance
* Verifying motor direction and timing entirely in assembly language
* Integrating multiple hardware subsystems into a single embedded application

---

## Future Improvements

* Implement full maze-learning and path memory
* Add intersection detection and decision-making
* Replace bang-bang steering with PID control
* Improve sensor calibration for varying lighting conditions

---

## What I Learned

This project strengthened my understanding of:

* Embedded systems programming
* Finite State Machine (FSM) design
* Interrupt-driven software
* Hardware/software integration
* Low-level debugging in assembly language
* Writing modular, maintainable embedded code

---

## Author

**Joshua Savunthararajah**
