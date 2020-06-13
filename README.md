# Autonomous-scaled-RC-Car.
The autonomous scaled rc is low-cost test platform designed for formula stdent driverless, which can be used to test the resulting program code with a real scaled vehicle. In addition, a virtual simulation of the algorithms is being set up in this area.
![rc](https://github.com/Dhaour9x/Autonomous-Low-Cost-RC_Car/blob/master/images/carbuild.gif)
## Hardware
![Hardware_Overview](https://github.com/Dhaour9x/Autonomous-Low-Cost-RC_Car/blob/master/images/hardware_overview.png)


This diagram shows all the components and their data & power connections.

   * Chasis (Redcat Racing Blackout SC 1/10) : The car chasis. It has adjustable 4x4 suspension and non-flat tires. It is also used for mounting things to it, including the housing which contains the computer and sensors.
  *  Computer (Jetson Nano): This the computer that runs the software on the car. You can connect to the computer in 3 ways primarily: ssh through local network to static IP, connecting to car's network and using ssh, or plugging a monitor, keyboard, and mouse into the computer directly.
   * Motor (Jrelecs F540 3930KV): The single DC motor that powers all four wheels. The motor makes the car move and is controlled by the VESC.
  *  Servo (ZOSKAY 1X DS3218): A servo is another type of motor but is better at going to specific angles along its rotation than rotating continuously. The servo's job is to steer the front wheels by taking in steering angle commands. The servo is also controlled by the VESC.
   * VESC (Turnigy SK8-ESC): The VESC is responsible for taking high level control commands like steering angle and velocity and converting that to power/angle commands for the motor/servo. The VESC has an associated ROS node. This node takes your ROS ackermann_msgs/AckermannDriveStamped message and converts that to VescStateStamped (power), and Float64 (steering angle) messages. These messages are something the physical VESC can use to control the motor and servo.
   * NiMH Battery (Redcat Racing HX-5000MH-B): There are 2 batteries. One to power the motor and in turn the VESC (because the motor power flows through the VESC). And a second to power the computer and sensors. Many of the issues (particularly with the VESC) can stem from one of these batteries having a low battery, so it is good to check them regularly.
    Power Converter (DZS Elec LM2596): This power converter converts the higher voltage of the battery to the necessary 5V max for the computer.
  *  RGBD Camera (Realsense D435i): This Intel Realsense camera can publish both rgb and depth. It has a associated node so you can just subscribe to the topic to use the images! OpenCV even has a function for converting ROS Image messages to something OpenCV can use. Note depth cameras are different from stereo cameras (how humans do it). They both provide the same output, but depth cameras project a IR pattern and use a IR camera to see the deformation of that pattern to compute depth. Depth cameras will also sometimes use stereo in addition to make their measurements more accurate. It publishes to the /camera topics. This camera can also publish IMU measurments, but they currently are not being used.
  *  Laser Scanner (YDLIDAR X4): This 360 degree sensor works by having a 1D laser range finder spin around. With each distance reading their is a associated angle the range finder was at. It publishes an array of distance and angle measurements to the /scan topic.
 *   Wireless Controller (Logitech F710): This provides controls to the cars! It doesn't just have to be use for teleop it can be used by your programs for most anything. It publishes on the /joy topic.
   * Micro SD Card: Storage for the OS and any logs. What's great about this is if you want to switch cars you can simply switch SD cards.


## Software
in development phase


## Installation


## Usage


## Component Documentation






@[Riadh Dhaoui](https://www.linkedin.com/in/riadh-dhaoui-2768b1167/)
