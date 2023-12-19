# Autonomous Lane Keeping and Color Detection for Mobile Robot via ROS

This project involves the development of an autonomous driving system for a differential drive mobile robot (Duckiebot). The architecture integrates computer vision algorithms for environment perception with closed-loop control strategies for navigation, orchestrated via the Robot Operating System (ROS).

## 1. Experimental Platform
The hardware platform is a differential drive mobile robot equipped with a Raspberry Pi and a monocular camera. It is configured to interact seamlessly within a ROS network for real-time data exchange.

<img alt="side" src="https://github.com/user-attachments/assets/2860809c-19cb-4dbe-aeec-46b3f5ca661b" width="49%"><img alt="back" src="https://github.com/user-attachments/assets/0f823d5c-ee27-43de-b30c-94b9b9779a72" width="49%">
<img alt="bottom" src="https://github.com/user-attachments/assets/ffe649b8-820e-4ab2-bfaf-31c51be9e57e" width="49%"><img alt="upper" src="https://github.com/user-attachments/assets/b6494445-f4c2-4d9a-add0-0c97e85189bb" width="49%">


---

## 2. Control Architecture and ROS Integration
The control and vision pipeline is designed in MATLAB/Simulink and deployed over a distributed ROS architecture. Custom nodes manage the communication by subscribing to the live camera feed and publishing velocity commands (`cmd_vel`) to the physical robot.

The system relies on a dual-loop control strategy:
* **Outer Loop (Perception and Kinematics):** Utilizes the Hough Transform and HSV filtering to compute lateral deviation, heading error, and target coordinates.
* **Inner Loop (Dynamics):** Regulates individual wheel velocities to track the generated references while compensating for the vehicle's non-holonomic constraints.

<img width="3611" height="2149" alt="scheme" src="https://github.com/user-attachments/assets/f87d0d87-85de-46c4-9533-34c81c58e57e" />

---

## 3. Experimental Results

The autonomous navigation functionalities were tested in a controlled environment to validate real-time performance and system stability.

### Lane Keeping
The perception system processes the camera feed to extract lane boundaries via the Hough Transform, allowing the controller to dynamically adjust the trajectory and maintain strict lane centering.

https://github.com/user-attachments/assets/2e4232ab-5e8d-4296-8e50-ace26acd3d31

### Color Detection
A vision-based recognition algorithm isolates specific color thresholds within the HSV space to detect and track targeted objects in the robot's field of view.

https://github.com/user-attachments/assets/2f0e7eda-e4b8-4218-9505-0b30b79e852d

### Integrated Lane Keeping and Color Detection
The fully integrated behavior demonstrates the system's capability to maintain lane discipline while simultaneously detecting and reacting to environmental markers in real time.

https://github.com/user-attachments/assets/e4c75951-4178-4b5d-8147-4ae4d21ee0e0

---

### Software and Hardware
* **ROS (Robot Operating System)**
* **MATLAB / Simulink**
* **Hardware:** Duckiebot (Differential Drive Mobile Robot)
