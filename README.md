# Building a Service Robot from Scratch
**Design, simulate, program, and prototype an autonomous mobile robot using ROS, OpenCV, PCL, and Python.**

This repository documents the development of an autonomous mobile robot, building on the project outlined in [Learning Robotics Using Python](https://www.packtpub.com/en-ic/product/learning-robotics-using-python-9781788623315), published by Packt. For more details on the original project, see the [Learning Robotics using Python - Second Edition](https://github.com/PacktPublishing/Learning-Robotics-using-Python-Second-Edition?tab=readme-ov-file) repository.

While this project follows the book’s framework, it includes updates to components and design choices to reflect newer hardware availability (post-2018) and my specific requirements. The aim is to create a low-cost service robot from scratch, providing practical experience in:
- Mechanical design with CAD software
- Robot simulation using ROS and Gazebo
- Electronics and sensor programming
- Algorithms for speech recognition, object detection, SLAM, etc.

## Mechanical Design of the Service Robot
This project focuses on building a miniature service robot for hotels and restaurants, designed to carry food and drinks. While real-world deployments might require a larger robot, this prototype is intended for technology testing and development.

### Requirements for the Service Robot
- **Payload Capacity:** Up to 5 kg
- **Speed:** 0.25 m/s to 1 m/s
- **Ground Clearance:** >3 cm
- **Battery Life:** 2 hours of continuous operation
- **Navigation:** Autonomous obstacle avoidance
- **Height:** 40 cm to 1 m
- **Cost:** Low-cost design

## Robot Drive Mechanism
The robot uses a **differential drive system** due it being cost-effective. It features two wheels on a common axis, each powered by an independent motor, and two caster wheels for stability and weight distribution.

![Differential Drive System](https://github.com/user-attachments/assets/84a7c129-b94c-487b-a105-bb5241a37050)

---
### Selection of Motors and Wheels
Motor and wheel choices are based on calculated speed and torque requirements:

- **RPM Calculation:**
  \[
  \text{RPM} = \frac{60 \times \text{Speed}}{\pi \times \text{Wheel Diameter}} = \frac{60 \times 0.35}{3.14 \times 0.09} \approx 74 \text{ RPM}
  \]
  *Note: Speed is taken as 0.35 m/s, the midpoint of the required speed range.*

- **Torque Calculation:**
  Assuming a total robot weight (including payload) of 15 kg, the torque per motor is calculated as:
  \[
  T = \frac{\mu \times W \times r}{2} = \frac{0.6 \times 15 \times 9.8 \times 0.045}{2} \approx 1.8 \text{ N-m} \text{ or } 18.35 \text{ kg-cm}
  \]
  where:
  - \(\mu\) = coefficient of friction (0.6)
  - \(W\) = total weight (15 kg)
  - \(r\) = wheel radius (0.045 m)
  - The factor of 2 accounts for the two driven wheels.

### Design Summary
- **Motor RPM:** 80 (selected to exceed the calculated 74 RPM)
- **Motor Torque:** 18.35 kg-cm (selected to meet the calculated requirement)
- **Wheel Diameter:** 9 cm

### Robot Chassis Design
After computing the robot's motor and wheel parameters, we can design the robot chassis or robot body. As required, the robot chassis should have a provision to hold food, it should be able to withstand up to 5 kg payload, the ground clearance of the robot should be greater than 3 cm and it should be low in cost. Apart from this, the robot should have a provision to place electronics components such as Personal Computer (PC), sensors, and battery.

One of the easiest designs to satisfy these requirements is a table-like design. The TurtleBot (http://www.turtlebot.com/) design is a kind of table-like design. It has three layers in the chassis. A robot platform called Roomba is the drive mechanism of this platform. The Roomba platform has motors and sensors inbuilt, so no need to worry about the designing of robot hardware.

![TurtleBot Chassis](https://github.com/user-attachments/assets/c9f2bb69-59a0-4150-8931-54ddbe2ce1c0)

To minimize costs and gain CAD experience, I’m designing the chassis from scratch using:

- **2D Modeling:** LibreCAD (free, open-source)
- **3D Modeling:** Blender (free, open-source)
- **3D Mesh Viewing:** MeshLab
- **Operating System:** Ubuntu (for ROS compatibility)

## Creating a 2D Drawing of the Robot

*[Placeholder: Add a description or image of the 2D design once completed.]*

## Creating a 3D Model of the Robot

## Robot Simulation with ROS and Gazebo

*[Placeholder: This section will detail the use of ROS and Gazebo to simulate the robot’s movement, sensor interactions, and environment. Include specific models or configurations once implemented.]*

---

## Selecting Hardware Components

This section outlines the hardware components chosen for the robot, balancing performance, cost, and compatibility.

### Hardware Specifications

*[Placeholder: Add detailed specs for each component once finalized.]*

---

#### Selecting Motors, Encoders, and Wheels

Motors are selected based on the calculated 80 RPM and 18.35 kg-cm torque requirements. Encoders will provide feedback for precise control, and wheels are sized at 9 cm in diameter.

---

#### Selecting a Motor Driver / Controller

*[Placeholder: Describe the motor driver selection, ensuring it supports the motors and integrates with the CPU.]*

---

#### Selecting the Ultrasonic Sensor

*[Placeholder: Explain the choice of ultrasonic sensor for obstacle detection.]*

---

#### Inertial Measurement Unit (IMU)

*[Placeholder: Detail the IMU selection for orientation and stability data.]*

---

#### Kinect

*[Placeholder: Describe the use of a Kinect sensor for depth perception and navigation.]*

---

#### CPU

*[Placeholder: Specify the CPU requirements for running ROS and processing sensor data.]*

---

#### Speakers / Mic

*[Placeholder: Outline the selection of speakers and a microphone for speech interaction.]*

---

#### Power Supply / Battery

*[Placeholder: Detail the battery choice to support 2 hours of operation under load.]*

---

### Hardware Summary & Integration

*[Placeholder: Provide an overview of how all components are integrated, including diagrams or schematics once available.]*

