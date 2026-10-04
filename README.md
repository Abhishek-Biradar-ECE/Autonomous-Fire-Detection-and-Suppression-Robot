Autonomous-Fire-Detection-and-Suppression-Robot

An Arduino-based Autonomous-Fire-Detection-and-Suppression-Robot developed using the
Arduino Uno. The robot is designed to detect fire using flame
sensors, navigate toward the detected fire source, and activate a water
pump for fire suppression. The project demonstrates sensor interfacing,
motor control, real-time decision making, and embedded firmware
development.



Overview

This project implements an Autonomous-Fire-Detection-and-Suppression-Robot using the
Arduino Uno.

The robot uses flame sensors to continuously monitor for a fire
source. The Arduino processes the sensor inputs and controls the DC
motors through an L298N motor driver to move the robot toward the
detected fire. A water pump is activated through a relay to suppress the
fire.

The project demonstrates the integration of sensors, motor drivers,
actuators, and embedded control logic into a single robotic system.

Features

Automatic flame detection

Autonomous movement toward the detected fire source

Real-time flame sensor monitoring

DC motor control using L298N motor driver

Automatic water pump activation

Relay-controlled water pump

Embedded control using Arduino Uno

Sensor-based decision making

Actuator control for fire suppression

Technologies Used

Programming Language: Arduino C/C++

Microcontroller: Arduino Uno

IDE: Arduino IDE

Motor Driver: L298N

Sensors: Flame Sensors

Actuator: Water Pump

Hardware / Peripherals {#hardware--peripherals}

Arduino Uno

Flame Sensors

L298N Motor Driver

DC Motors

Water Pump

Relay Module

Robot Chassis

Battery Pack

How It Works

When the robot is powered on, the flame sensors continuously monitor the
surroundings for a fire source.

The Arduino Uno reads the flame sensor inputs and processes them using
programmed control logic.

When a flame is detected, the Arduino controls the L298N motor
driver to drive the DC motors and move the robot toward the detected
fire source.

Once the robot reaches the required position, the Arduino activates the
relay and water pump to spray water and suppress the fire.

The robot continuously monitors the flame sensors and performs the
programmed actions based on the sensor inputs.

System Flow

       Flame Sensors
             |
             v
      +--------------+
      |  Arduino Uno |
      | Control Logic|
      +--------------+
          |       |
          |       |
          v       v
    L298N Motor   Relay
      Driver       |
          |        v
          v    Water Pump
      DC Motors
          |
          v
    Robot Movement

    Flame Detection
          |
          v
    Fire Suppression

Firmware Modules

The project is implemented as a single Arduino firmware program.

File                       Description

firefighting_robot.ino   Main Arduino program and control logic

Embedded Systems Concepts Demonstrated

Embedded C/C++ programming

Arduino microcontroller programming

GPIO configuration

Digital sensor interfacing

Flame sensor interfacing

Motor driver control

DC motor control

Relay control

Water pump control

Real-time sensor monitoring

Conditional control logic

Autonomous robotic control

Sensor-based decision making

Hardware-software integration

Actuator interfacing

Project Workflow

The robot follows a sensor-based control process to detect and suppress
fire.

Start
  |
  v
Initialize Arduino
  |
  v
Read Flame Sensors
  |
  v
Flame Detected?
  |
  +------ No ------> Continue Monitoring
  |
 Yes
  |
  v
Determine Movement
  |
  v
Control DC Motors
  |
  v
Move Toward Fire
  |
  v
Activate Water Pump
  |
  v
Suppress Fire
  |
  v
Continue Monitoring

Circuit Diagram

The following image shows the circuit used for the fire-fighting robot.



How to Run

Open the firefighting_robot.ino file in Arduino IDE.

Connect the Arduino Uno to the computer.

Select the appropriate Arduino board and COM port.

Compile and upload the program to the Arduino Uno.

Assemble the robot according to the circuit diagram.

Power the robot using the appropriate battery supply.

Place a controlled flame source within the detection range of the
flame sensors.

The robot detects the flame, moves toward it, and activates the
water pump for fire suppression.

Safety: Test the fire-detection and water-pump system in a
controlled environment with appropriate safety precautions.

Project Structure

Autonomous-Firefighting-Robot/
│
├── README.md
├── firefighting_robot.ino
└── circuit_image.png

Future Improvements

Obstacle avoidance using ultrasonic sensors

Servo-based water nozzle positioning

Wireless monitoring and control

Smoke and temperature sensing

IoT-based fire alerts

Mobile application for remote monitoring

Improved fire localization using multiple flame sensors

Author

Abhishek Biradar

B.E. Electronics & Communication Engineering

Embedded Systems | Firmware Development | Robotics | IoT
