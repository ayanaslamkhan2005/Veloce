# VELOCE – Bluetooth-Controlled Robotic Car Using Arduino

> **Small machine. Big motion.**

## 🚗 Project Overview

**VELOCE** is a Bluetooth-controlled robotic car developed using Arduino microcontrollers, wireless communication modules, and an L298N motor driver.

The system consists of two Arduino-based units: a transmitter and a receiver. The transmitter reads analog inputs from a controller, converts them into directional commands, and transmits them wirelessly through Bluetooth. The receiver processes these commands and controls the movement of the robotic car through the motor driver.

The car supports five basic operations: forward, backward, left, right, and stop.

This project demonstrates the practical integration of embedded systems, wireless communication, electronics, and robotics.

## 🎯 Objectives

- Design and develop a wireless robotic car using Arduino.
- Establish Bluetooth communication between separate transmitter and receiver units.
- Convert analog controller inputs into directional movement commands.
- Implement motor control using an L298N motor driver.
- Understand embedded programming and hardware integration.
- Gain practical experience in robotics and wireless communication.

## ⚙️ Components Used

| Component | Purpose |
|---|---|
| Arduino Microcontrollers (2) | Transmitter and receiver control units |
| HC-05 Bluetooth Modules | Wireless communication |
| Analog Input Modules | Directional input for the transmitter |
| L298N Motor Driver | Controls motor direction |
| DC Motors | Provide movement to the car |
| Robotic Car Chassis | Mechanical structure |
| Battery | Power supply |
| Connecting Wires | Electrical connections |

*Note: Confirm the exact Bluetooth module count and analog input hardware against your physical setup before publishing.*

## 🔍 Working Principle

VELOCE operates through wireless communication between an Arduino transmitter and an Arduino receiver.

### 1. Input Detection

The transmitter Arduino reads analog values from pins A0 and A1. These values represent directional inputs from the controller.

### 2. Command Processing

The transmitter processes the analog readings using predefined threshold conditions to determine the required movement.

The following commands are generated:

| Command | Function |
|---|---|
| F | Forward |
| B | Backward |
| L | Left |
| R | Right |
| N | Neutral / Stop |

### 3. Bluetooth Communication

The generated commands are transmitted wirelessly to the receiver through Bluetooth communication at a baud rate of 9600.

The SoftwareSerial library is used to establish serial communication through Arduino digital pins 2 and 3.

### 4. Command Reception

The receiver Arduino continuously checks for incoming Bluetooth data. Once a command is received, it identifies the corresponding movement instruction.

### 5. Motor Control

Based on the received command, the receiver controls digital output pins 10, 11, 12, and 13, which are connected to the L298N motor driver's input pins.

The motor driver controls the direction of rotation of the DC motors, allowing VELOCE to move according to the transmitted commands.

## 🕹️ Control Mapping

| Input Condition | Command | Car Movement |
|---|---|---|
| A1 ≥ 375 | F | Forward |
| A1 ≤ 320 | B | Backward |
| A0 ≥ 375 | R | Right |
| A0 ≤ 315 | L | Left |
| No directional condition | N | Stop |

## ✨ Features

- Wireless control through Bluetooth communication.
- Separate Arduino transmitter and receiver units.
- Analog input-based directional control.
- Forward and backward movement.
- Left and right turning.
- Stop functionality.
- Real-time command transmission and processing.

## 📂 Repository Structure

```text
Veloce-Bluetooth-Controlled-Robotic-Car/
│
├── README.md
│
├── Code/
│   ├── transmitter.ino
│   └── receiver.ino
│
└── Images/
    ├── VeloceRemoteCar.jpeg
    └── VeloceCarAlongWithMe.jpeg
```

## 💻 Code Description

### 1. Transmitter (`transmitter.ino`)

- Reads analog values from Arduino pins A0 and A1.
- Evaluates the input values against predefined thresholds.
- Generates directional commands (F, B, L, R, N).
- Transmits commands wirelessly through the Bluetooth module.

### 2. Receiver (`receiver.ino`)

- Receives incoming Bluetooth commands.
- Identifies the corresponding movement instruction.
- Controls digital output pins 10, 11, 12, and 13.
- Sends appropriate signals to the L298N motor driver to operate the robotic car.

## 🛠️ Technologies Used

- **Programming Language:** C/C++
- **Microcontroller Platform:** Arduino
- **Wireless Communication:** Bluetooth
- **Library:** SoftwareSerial
- **Hardware Control:** L298N Motor Driver
- **Domain:** Robotics and Embedded Systems

## 🚀 Future Improvements

- Integration of ultrasonic sensors for obstacle detection.
- Implementation of PWM-based motor speed control.
- Development of a smartphone application for wireless control.
- Addition of autonomous navigation capabilities.
- Integration of additional sensors for intelligent movement.

## 🌍 Potential Applications

- Educational robotics and embedded systems projects.
- Wireless robotic vehicle control.
- Remote-controlled automation systems.
- Foundation for autonomous robotic applications.

## 📸 Project Demonstration

Photographs and circuit diagrams of VELOCE can be found in the `Images/` directory.

*Project demonstration video can be added here.*

## 👨‍💻 Project Information

| Detail | Description |
|---|---|
| Project Name | VELOCE |
| Project Type | Academic Hardware Project |
| Domain | Robotics and Embedded Systems |
| Platform | Arduino |
| Communication | Bluetooth |

---

**VELOCE – Small machine. Big motion.**

Built to explore the intersection of electronics, programming, wireless communication, and robotics.
