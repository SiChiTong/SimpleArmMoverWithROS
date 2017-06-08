# Simple Arm Mover Simulation With ROS
Ros Nodes are a key abtraction that allows a robot system to be build modularly.
This is an example of writing ROS nodes in Python.
## Node and Topics
### ROS
Robot Operating System(ROS) provides a powerful communication system allowing these different components to communicate with one another.
* **Perception**
  * Robots contain sensor for  perceiving the world around them.
* **Decision Making**
  * Software for making high level decisions.
* **Actuation**
  * Motors and Controllers fractionation.
Ross manages these three complex steps by breaking each of them down into many small Unix processes called **nodes**. Typically each node on the system is responsible for one small and relatively specific portion of the robot's overall functionality.
###### For example:
There may be nodes for each sensor and actuator in the system as well as nodes for things like *position estimation*(Perception), *behavior execution*(Decision Making) and *motor control*(Actuation).

### ROS Master Process
At the center of these collection of nodes is ROS Master Process which acts as a sort of manager of all the nodes. The ROS master maintains a registry of all the active nodes on a system.  It then allows each node to discover other nodes in the system and establish lines of communication with them. In addition to allowing nodes to locate one another and communicate, the ROS master also hosts what's called the parameter server.

#### The parameter server
As it name suggest, it is typically used to store parameters and configuration values that are shared amongst the running nodes.
###### For example:
A mobile robots wheel radius such as [BlueBot](https://github.com/fouliex/BlueBot) may be used by one node to estimate position and by another to calculate speed. Rather then storing the same information in multiple places nodes can look up the values as needed.

### Topic
Nodes can also share data with one another by passing messages over what are called topics.
A topic is simply named bus which we can  think of as a pipe between nodes through which messages flow. 
* Publish
  * In order to send a message on a topic, we say that anode was published to it.
* Subscribe
  * Likewise to receive a message on a topic I know and must subscribe to it.

## Message Passing
Each ROS distribution comes with a variety of predefined message types which are available for your use.
There are message types for communicating physical quantities such as
* Positions
* Velocities
* Accelerations
* Rotations
* Durations

There are also messages for communicating sensor readings such as:
* Laser Scans
* Images
* Point Clouds
* Inertial Measurements
It's important to note that although the named messages would seem to imply text based contents they can in fact contain any kind of data.


##  Project Nodes
* simple_mover-publish joint angle to simple_arm
* arm_mover-provides a service called safe_mode
* safe_move-allows the arm to be moved to any position within its workspace.
**The safe zone is bounded my minimum and maximum joint angles, and is configurable via the ROS' parameter server

###### Simple Arm Mover 
![Simple Arm](https://github.com/fouliex/SimpleArmMoverWithROS/blob/master/misc/simple_arm.gif)
