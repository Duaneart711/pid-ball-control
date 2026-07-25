# PID Ball Control System

## Overview

Designed and built a closed-loop ball-and-beam control system that uses a PID (Proportional–Integral–Derivative) controller to keep a ball near a target position in real time. The project combines embedded programming, sensors, mechanical hardware, and feedback control to continuously monitor the ball's position and adjust the beam angle.

Using an Arduino Uno, a Sharp infrared distance sensor, and a servo motor, the system continuously measures the ball's position and corrects it by tilting the beam. Through repeated testing and controller tuning, the system achieved stable ball positioning with improved response time and reduced oscillations.

---

## Hero Photo

<img width="1179" height="869" alt="IMG_2273" src="https://github.com/user-attachments/assets/b654d8fe-0a8d-4ae6-9bc8-299f7274bf58" />

---

### Labeled System Overview

<img width="1179" height="664" alt="IMG_2300" src="https://github.com/user-attachments/assets/26506dfa-74c9-4404-93d6-da5381ca6223" />

<img width="2054" height="1149" alt="IMG_2055" src="https://github.com/user-attachments/assets/189bc0db-174e-49d1-b8a0-8135e3f90d58" />

---

## How It Works

The system uses a Sharp infrared distance sensor to continuously measure the position of the ball on the beam. Every 50 milliseconds, the Arduino reads the sensor, calculates how far the ball is from its target position, and determines how much the servo motor should tilt the beam.

A PID controller makes these adjustments by considering three factors:

- **Proportional (P):** Corrects the current position error.
- **Integral (I):** Removes small errors that remain over time.
- **Derivative (D):** Reduces overshoot and helps stabilize the ball's movement.

The controller output is converted into a servo angle, allowing the beam to respond smoothly and keep the ball near the desired position.

<img width="1179" height="332" alt="IMG_2302" src="https://github.com/user-attachments/assets/6bc9d572-615a-4f31-b387-7a92ee592c13" />

---

## Code

The snippet below illustrates the core PID control loop responsible for reading the sensor, computing the control output, and commanding the servo motor.

```cpp
distance = get_dist(100);

distance_error = distance_setpoint - distance;
PID_p = kp * distance_error;

float dist_difference = distance_error - distance_previous_error;
PID_d = kd * (dist_difference / period);

if (-3 < distance_error && distance_error < 3)
{
    PID_i += ki * distance_error;
}
else
{
    PID_i = 0;
}

PID_total = PID_p + PID_i + PID_d;
PID_total = map(PID_total, -150, 150, 0, 150);

if (PID_total < 20) PID_total = 20;
if (PID_total > 160) PID_total = 160;

myservo.write(PID_total + 30);

distance_previous_error = distance_error;
```
---

## Hardware Components

The control system combines embedded electronics with a custom mechanical assembly to continuously measure the ball's position and adjust the beam angle in real time.

- Arduino Uno
- Sharp GP2Y0A21 Infrared Distance Sensor
- Servo Motor
- Ball-and-Beam Assembly
- Custom Mechanical Linkage
- 3D Printed Support Structure
- Wooden Base
- Jumper Wiring and Power Distribution

---

## Design & Implementation

This project was designed, built, programmed, and tested from start to finish. Development included hardware assembly, embedded programming, controller tuning, and experimental validation.

Key work completed included:

- Designed and assembled the complete ball-and-beam system.
- Programmed the PID control algorithm using an Arduino Uno.
- Integrated the infrared distance sensor with the servo-controlled beam.
- Wired and tested the electrical and mechanical components.
- Tuned the proportional, integral, and derivative gains through repeated testing.
- Troubleshot sensor noise, controller stability, and mechanical response.
- Evaluated controller performance using experimental response data.
---

## Engineering Challenges

Developing a stable control system required balancing fast response with overall stability.

- **PID tuning:** Finding the right combination of proportional, integral, and derivative gains required multiple rounds of testing to achieve quick response without excessive overshoot.

- **Sensor accuracy:** The infrared distance sensor produced small measurement fluctuations, so multiple readings were averaged before each control update to improve stability.

- **Mechanical limitations:** Because the servo motor cannot move instantly, the controller had to account for mechanical delay while minimizing unnecessary oscillations.
---

## Testing & Validation

System performance was evaluated by adjusting the PID gains and measuring how the controller responded under different operating conditions.

Performance was evaluated using:

- Rise Time
- Peak Overshoot
- Settling Time
- Steady-State Error
- Position Error Standard Deviation

These measurements were used to compare different controller settings and guide the tuning process until stable system performance was achieved.

---

## Results

The completed system successfully demonstrated stable closed-loop PID control by continuously balancing the ball near its target position. Through iterative tuning and repeated testing, the controller achieved smoother motion, reduced overshoot, and improved settling time while maintaining reliable operation across multiple test runs.

The project demonstrated the successful integration of embedded programming, sensor feedback, servo control, and real-time control algorithms into a functioning closed-loop control system.
---

## Project Photos

##Electrical Integration

The diagram below shows the electrical connections between the Arduino Uno, Sharp GP2Y0A21 infrared distance sensor, and servo motor used to implement the closed-loop control system.

<img width="1179" height="874" alt="IMG_2301" src="https://github.com/user-attachments/assets/0c6ee039-4ebc-45ba-8a6f-2dcbe2adcca9" />

##Additional Build Photo

<img width="1178" height="1511" alt="IMG_1988" src="https://github.com/user-attachments/assets/2820d5e3-a9c1-4ebd-9c5a-89b3dbace256" />

---

## Demonstration

> **Note:** GitHub limits embedded video uploads to 10 MB, so the embedded demonstrations below are compressed highlight clips. Full-resolution demonstrations are available through the YouTube Shorts links below.

### Embedded Demonstrations

https://github.com/user-attachments/assets/2e9c9706-b074-4bcb-9ad0-9f6cbc69de67

https://github.com/user-attachments/assets/6ab9d0d0-97cc-41aa-9621-f464d09bdb7d

### High-Quality Demonstrations

- YouTube Short 1: https://youtube.com/shorts/YnTExcN106Y?feature=share
- YouTube Short 2: https://youtube.com/shorts/EXuupr8XJpA?feature=share

---

## Skills Demonstrated

- PID Control
- Embedded Systems
- Arduino Programming
- Sensor Integration
- Servo Motor Control
- Hardware Integration
- Electrical Wiring
- Hardware Testing
- Troubleshooting
- System Validation
- Electromechanical Systems
- Prototype Development
