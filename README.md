# MicroMouse Electrical Systems

Electrical systems development for an autonomous MicroMouse robot designed for maze navigation and competition.

---

## Overview

This project covers the design, testing, and development of the MicroMouse electrical system as part of the IEEE MicroMouse team at the University of Georgia.

My work focused exclusively on the **electrical systems**, including circuit design, sensor development, motor-control hardware, PCB design, and hardware testing.

### Electrical System

The robot's electrical system includes:

* STM32-based control hardware
* Infrared wall-detection sensors
* Brushed DC motor control
* IMU interface
* Power regulation and distribution
* Custom PCB designed in Altium Designer

---

## Contributions

* Designed and tested infrared wall-detection circuitry, including signal filtering and conditioning
* Investigated sensor response using multimeter and oscilloscope measurements
* Tested brushed DC motor PWM control using an oscilloscope and function generator
* Designed the electrical system PCB in Altium Designer as part of a three-person design group
* Completed schematic capture, PCB layout, routing, and design-rule checks
* Generated Gerber files for PCB manufacturing
* Soldered and tested STM32 hardware and supporting circuitry
* Investigated electrical failures from the previous competition board, including unreliable wall detection and H-bridge failures
* Proposed improvements to the IR sensing circuitry to increase wall-detection reliability

---

## Hardware Design

The electrical system was developed around several major hardware subsystems:

**Sensors**

* Infrared wall-detection circuitry
* Signal filtering and conditioning
* IMU interface

**Motor Control**

* Brushed DC motors
* Motor-driver circuitry
* PWM control interface

**Power**

* Power regulation
* Power distribution
* Supporting decoupling and protection circuitry

**Control Hardware**

* STM32 microcontroller
* Sensor and motor interfaces
* Supporting circuitry

### Schematic

![MicroMouse Schematic]

### PCB Layout

![MicroMouse PCB Layout]

### 3D PCB View

![MicroMouse PCB]

---

## Testing & Development

The electrical system was developed through an iterative process of circuit design, prototyping, measurement, debugging, and PCB revision.

Testing included:

* IR sensor characterization
* Signal and filtering measurements
* Motor PWM testing
* Power-system testing
* STM32 hardware bring-up
* PCB electrical verification

Particular attention was given to improving the reliability of the infrared wall sensors and motor-control circuitry after electrical issues were identified on the previous competition board.

---

## Documentation

### Electrical Design

* [System Overview]
* [Electrical Design]
* [IR Sensors]
* [Motor Control]
* [Power System]
* [STM32 Hardware]

### PCB Design

* [PCB Design]
* [Schematic Files]
* [PCB Files]
* [Manufacturing Files]

### Testing & Development

* [Testing & Debugging]
* [Design History]

---

## Tools & Technologies

**Hardware:** STM32 · IR Sensors · Brushed DC Motors · IMU · Power Regulation

**Design:** Altium Designer · Schematic Capture · PCB Layout · PCB Routing · Gerber Generation

**Testing:** Oscilloscope · Function Generator · Multimeter

---

## Project Status

**Active Development**

Current work is focused on improving the electrical system for future MicroMouse competition use, with an emphasis on reliable wall detection, motor control, and overall board robustness.
