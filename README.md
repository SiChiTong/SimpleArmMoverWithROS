# Simple Arm Mover Simulation With ROS
Ros Nodes are a key abtraction that allows a robot system to be build modularly.
This is an example of writing ROS nodes in Python.
## Node and Topics
ROS provides a powerful communication system allowing these different components to communicate with one another.
* **Perception**
  * Robots contain sensor for  perceiving the world around them.
* **Decision Making**
  * Software for making high level decisions.
* **Actuation**
  * Motors and Controllers fractionation.
Ross manages these three complex steps by breaking each of them down into many small Unix processes called **nodes**. Typically each node on the system is responsible for one small and relatively specific portion of the robot's overall functionality.
###### For example:
There may be nodes for each sensor and actuator in the system as well as nodes for things like *position estimation*(Perception), *behavior execution*(Decision Making) and *motor control*(Actuation) .
## Nodes
* simple_mover-publish joint angle to simple_arm
* arm_mover-provides a service called safe_mode
* safe_move-allows the arm to be moved to any position within its workspace.
**The safe zone is bounded my minimum and maximum joint angles, and is configurable via the ROS' parameter server

###### Simple Arm Mover 
![Simple Arm](https://github.com/fouliex/SimpleArmMoverWithROS/blob/master/misc/simple_arm.gif)
