# Building a Service Robot from Scratch
**Design, simulate, program, and prototype an autonomous mobile robot using ROS, OpenCV, PCL, and Python.**

This code repository follows the project detailed in [Learning Robotics Using Python](https://www.packtpub.com/en-ic/product/learning-robotics-using-python-9781788623315), published by Packt. For further details and instructions on the book, see the [Learning Robotics using Python - Second Edition](https://github.com/PacktPublishing/Learning-Robotics-using-Python-Second-Edition?tab=readme-ov-file) repository.

This repository follows the project detailed in the book, except where mentioned. Since the book is from 2018, I have updated some of the parts and made minorly different design decisions based on new parts and my own requirements for the robot. The purpose of this project for me was to build a low-cost robot from scratch that would allow me to learn and apply mechanical design in CAD software, robot simulation with ROS and Gazebo, programming electronics and sensors, and algorithms for speech recognition and synthesis, object detection, SLAM, etc.

# Mechanical Design of the Service Robot
The robot that we are going to build is used as a service robot in hotels and restaurants to serve food and drinks. The actual robot deployed in hotels may be big, but here we are intending to build a miniature version of it only for testing our technology.

## The Requirements for the Service Robot
- The robot should have a provision to carry food
- The robot should be able to carry a maximum payload of 5 kg
- The robot should travel at a speed between 0.25 m/s and 1 m/s
- The ground clearance of the robot should be greater than 3 cm
- The robot must be able to work for 2 hours continuously
- The robot should be able to move and supply food to any table avoiding obstacles
- The robot height should be between 40 cm and 1 meter
- The robot should be of low cost

## Robot Drive Mechanism
- One of the cost effective solution for mobile robot navigation is differential drive systems. It's one of the simplest drive mechanisms for a mobile robot that is mainly indented for indoor navigation. The differential drive robot consists of two wheels mounted on a common axis controlled by two separate motors. There are two supporting wheels called caster wheels. It ensures stability and weight distribution of the robot. The following diagram shows a typical differential drive system:
    ![image](https://github.com/user-attachments/assets/84a7c129-b94c-487b-a105-bb5241a37050)

### Selection of Motors and Wheels
- Motors are selected after looking at their specifications. Some of the important parameters for motor selection are torque and RPM.
    RPM = ((60 * Speed /(3.14 * Diameter of Wheel)
    RPM = (60 * 0.35 )/(3.14 * 0.09) = 21 / 0.2826 = 74 RPM
- We can write the frictional force as robot torque = 0 until the robot moves. If we get the robot torque in this condition, we get the maximum torque as follows:
    µ * N * r - T = 0, where µ is the coefficient of friction, N is the average weight acting on each wheel, r is the radius of wheels, and T is the torque.
    N = W/4 ( assuming that the weight of the robot is equally distributed on all the four wheels)
- Therefore, we get:
    0.6 * (150/4) * 0.045 - T = 0
- Hence, T = 1.0125 N-m or 10.32 Kg-cm

### Design Summary
- Motor RPM = 80
- Motor Torque = 10.32 kg-cm
- Wheel diameter = 9 cm

### Robot Chassis Design
- After computing the robot's motor and wheel parameters, we can design the robot chassis or robot body. As required, the robot chassis should have a provision to hold food, it should be able to withstand up to 5 kg payload, the ground clearance of the robot should be greater than 3 cm and it should be low in cost. Apart from this, the robot should have a provision to place electronics components such as Personal Computer (PC), sensors, and battery.
- One of the easiest designs to satisfy these requirements is a table-like design. The TurtleBot (http://www.turtlebot.com/) design is a kind of table-like design. It has three layers in the chassis. A robot platform called Roomba is the drive mechanism of this platform. The Roomba platform has motors and sensors inbuilt, so no need to worry about the designing of robot hardware. The following figure shows the TurtleBot robot chassis design:
![image](https://github.com/user-attachments/assets/c9f2bb69-59a0-4150-8931-54ddbe2ce1c0)
- In order to keep costs low and because I want to practice using CAD software, I'm going to design a TurtleBot-like chassis from scratch.
- Following the book, I use a 2D model in LibreCAD and a 3D model in Blender, since they're free and OS agnostic.
- We also use a 3D mesh viewing tool called MeshLab to view and check the 3D model design and use Ubuntu as the main OS.

## Creating a 2D Drawing of the Robot

## Creating a 3D Model of the Robot

# Robot Simulation with ROS and Gazebo

# Selecting Hardware Components

## Hardware Specifications

## Selecting Motors, Encoders, and Wheels

## Selecting a Motor Driver / Controller

## Selecting the Ultrasonic Sensor

## Inertial Measurement Unit (IMU)

## Kinect

## CPU

## Speakers / Mic

## Power Supply / Battery

## Hardware Summary & Integration


