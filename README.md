# PID Ball Control System

## Overview

Designed and built a closed-loop ball-and-beam control system that uses a PID (Proportional–Integral–Derivative) controller to keep a ball at a target position in real time. The project combines embedded programming, sensors, mechanical hardware, and feedback control to adjust the beam angle as the ball moves automatically.

Using an Arduino Uno, a Sharp infrared distance sensor, and a servo motor, the system continuously measures the ball's position and corrects it by tilting the beam. Through repeated testing and controller tuning, the system achieved stable ball positioning with improved response time and reduced oscillations.

---

## Hero Photo

<img width="1179" height="869" alt="IMG_2273" src="https://github.com/user-attachments/assets/b654d8fe-0a8d-4ae6-9bc8-299f7274bf58" />

---

## Project Highlights

- Closed-loop PID control system
- Arduino-based embedded programming
- Real-time position feedback using an infrared distance sensor
- Servo motor beam control
- PID tuning and controller optimization
- Hardware integration and electrical wiring
- Experimental testing and performance evaluation

---

## How It Works

The system uses a Sharp infrared distance sensor to continuously measure the position of the ball on the beam. Every 50 milliseconds, the Arduino reads the sensor, calculates how far the ball is from its target position, and determines how much the servo motor should tilt the beam.

A PID controller makes these adjustments by considering three factors:

- **Proportional (P):** Corrects the current position error.
- **Integral (I):** Removes small errors that remain over time.
- **Derivative (D):** Reduces overshoot and helps stabilize the ball's movement.

The controller output is converted into a servo angle, allowing the beam to respond smoothly and keep the ball near the desired position.

---

## Code

The snippet below shows the core control loop that reads the sensor, calculates the PID output, and adjusts the servo to keep the ball centered.

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

- Arduino Uno
- Sharp GP2Y0A21 Infrared Distance Sensor
- Servo Motor
- Ball-and-Beam Assembly
- Custom Mechanical Linkage
- 3D Printed Support Structure
- Wooden Base
- Jumper Wiring and Power Distribution

---

## My Contributions

This project involved designing, programming, assembling, and testing the complete control system.

My responsibilities included:

- Programming the PID control algorithm on an Arduino Uno.
- Integrating the infrared distance sensor with the servo-controlled beam.
- Wiring and assembling the electrical and mechanical components.
- Tuning the proportional, integral, and derivative gains through repeated hardware testing.
- Troubleshooting sensor noise, unstable controller behavior, and mechanical response issues.
- Evaluating controller performance using experimental response data.

---

## Engineering Challenges

One of the biggest challenges was tuning the PID controller to keep the ball stable while still responding quickly. Higher proportional gains improved response speed but caused overshoot, while excessive derivative gain reduced oscillations at the cost of slower movement. The controller required several rounds of tuning to find the right balance between speed and stability.

Another challenge was reducing noise from the infrared distance sensor. To improve measurement accuracy, the controller averaged multiple sensor readings before calculating each control update.

The mechanical system also introduced limitations. Since the servo motor cannot move instantly, the controller had to be tuned to account for the physical response of the beam while minimizing delay and preventing unnecessary oscillations.

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

The completed system successfully maintained the ball near its desired position using real-time PID control. Through iterative tuning and repeated testing, the controller became more stable, reduced overshoot, and improved settling time while maintaining reliable operation throughout multiple test runs.

---

## Project Photos

### Labeled System Overview

<img width="2054" height="1149" alt="IMG_2055" src="https://github.com/user-attachments/assets/189bc0db-174e-49d1-b8a0-8135e3f90d58" />

### Additional Build Photo

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
