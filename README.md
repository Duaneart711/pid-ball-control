# PID Ball Control System

## Overview

Designed and built a closed-loop ball-and-beam control system that stabilizes a ball at a desired position using real-time PID (Proportional–Integral–Derivative) control. The project combines embedded programming, sensor integration, electromechanical actuation, and feedback control to continuously measure the ball's position and adjust the beam angle using a servo motor.

The system was implemented using an Arduino Uno, a Sharp GP2Y0A21 infrared distance sensor, and a servo-driven beam mechanism. The controller was iteratively tuned through experimental testing to improve response time, reduce steady-state error, minimize overshoot, and achieve stable ball positioning under varying initial conditions.

---

## Hero Photo

<img width="1179" height="869" alt="IMG_2273" src="https://github.com/user-attachments/assets/b654d8fe-0a8d-4ae6-9bc8-299f7274bf58" />

---

## Project Highlights

- Closed-loop PID control implementation
- Real-time position feedback using a Sharp GP2Y0A21 infrared distance sensor
- Servo motor beam actuation
- Arduino-based embedded control system
- PID gain tuning and controller optimization
- Hardware integration and electrical wiring
- Electromechanical system design
- Experimental controller performance evaluation

---

## System Description

The system continuously measures the position of a ball along a beam using a Sharp infrared distance sensor. Position measurements are processed by an Arduino Uno running a PID control algorithm that calculates the difference between the desired and measured ball position.

The controller generates a corrective output that adjusts the servo motor angle, changing the inclination of the beam to move the ball toward the desired position. This feedback loop executes every 50 milliseconds, allowing the controller to compensate for disturbances and maintain stable ball positioning continuously.

---

## Hardware Components

- Arduino Uno
- Sharp GP2Y0A21 Infrared Distance Sensor
- Servo Motor
- Ball-and-Beam Mechanical Assembly
- Custom Mechanical Linkage
- 3D Printed Support Structure
- Wooden Base
- Jumper Wiring and Power Distribution

---

## Control Strategy

The Arduino continuously sampled the Sharp infrared distance sensor to determine the ball's position along the beam. To improve measurement stability, the controller averaged 100 sensor readings before calculating the control error.

A proportional–integral–derivative (PID) controller computed the difference between the desired ball position and the measured position. The proportional term corrected the current position error, the integral term reduced steady-state error when the ball remained near the target position, and the derivative term damped oscillations by responding to changes in the error over time.

The combined controller output was mapped to a servo motor angle that adjusted the beam inclination. Output limits were applied to prevent excessive servo movement while maintaining stable closed-loop operation. Controller gains were iteratively tuned through hardware testing to improve responsiveness while minimizing overshoot, oscillation, and settling time.

---

## Engineering Responsibilities

- Designed and integrated the embedded control system using an Arduino Uno and a Sharp infrared distance sensor.
- Programmed and implemented a closed-loop PID controller for real-time ball position stabilization.
- Integrated the servo motor, infrared sensor, and mechanical beam assembly into a complete electromechanical system.
- Tuned proportional, integral, and derivative gains through iterative testing to improve controller performance.
- Investigated sensor noise, controller oscillations, and mechanical limitations through systematic hardware testing and troubleshooting.
- Validated controller performance through experimental testing using multiple system response metrics.

---

## Engineering Challenges

Developing a stable closed-loop controller required balancing fast response with overall system stability. Increasing proportional gain improved response speed but introduced overshoot, while excessive derivative gain reduced oscillations at the expense of slower motion. Integral gain was carefully adjusted to reduce steady-state error without causing instability.

Another challenge involved reducing measurement noise from the Sharp infrared distance sensor. To improve measurement reliability, multiple sensor readings were averaged before each control update, reducing fluctuations that could negatively affect controller performance.

Mechanical limitations also influenced system behavior. Because the servo motor and beam mechanism required finite time to respond, controller tuning had to account for actuator response, mechanical inertia, and latency while maintaining smooth ball movement and minimizing oscillations.

---

## Testing & Validation

Controller performance was evaluated by experimentally varying the proportional, integral, and derivative gains while measuring key control system characteristics, including:

- Rise Time
- Peak Overshoot
- Settling Time
- Steady-State Error
- Position Error Standard Deviation

Controller gains were iteratively refined using these measurements to improve overall system performance and achieve stable closed-loop control under varying operating conditions.

---

## Results

The completed system successfully stabilized the ball using real-time closed-loop PID control. Through iterative controller tuning and repeated hardware testing, the system achieved stable ball positioning with reduced steady-state error, controlled overshoot, and improved settling time. Experimental evaluation demonstrated the effect of individual PID gains on controller performance while validating the effectiveness of the implemented feedback control strategy.

---

## Project Photos

### Complete System


### Additional Build Photo

*(Insert the additional system photo here.)*

---

## Demonstration

> **Note:** GitHub limits embedded video uploads to 10 MB, so the embedded demonstration is a compressed highlight clip. Higher-quality demonstrations are available through the YouTube Shorts links below.

### Embedded Demonstration

https://github.com/user-attachments/assets/5e7e4817-be4a-4190-be47-2c6e6f99ee15

https://github.com/user-attachments/assets/20f6ba15-5b47-49eb-a0a7-02d0c3827354


### High-Quality Demonstrations

- YouTube Short 1: (https://youtube.com/shorts/YnTExcN106Y?feature=share)
- YouTube Short 2: (https://youtube.com/shorts/EXuupr8XJpA?feature=share)
  
---

## Skills Demonstrated

This project strengthened practical experience in:

- PID Control
- Embedded Systems
- Control Systems
- Arduino Programming
- Sensor Integration
- Servo Motor Control
- Hardware Integration
- Electrical Wiring
- Electrical Testing
- Hardware Troubleshooting
- System Validation
- Feedback Control
- Electromechanical System Design
- Prototype Development
