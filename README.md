# Line Following and ArUco Parking Car

This file provides instructions on how to use this package.

### Contents 

- [ArUco Marker Recognition and Its Use for Pose Estimation](https://github.com/SunstanYu/EE346_Line_Follower.git)
- [LiDAR-Based Navigation with TurtleBot3](https://github.com/SunstanYu/EE346_Lab6.git)
- [Autonomous Navigation with SMACH](https://github.com/SunstanYu/EE346_Lab7.git)

### Usage

1. Clone source code

   ```bash
   cd ~/catkin_ws/src
   git clone git@github.com:SunstanYu/Line_Follower_Turtlebot3.git
   ```

2. Catkin make

   ```bash
   cd ..
   catkin_make
   ```

3. On PC

   ```bash
   roscore
   ```

4. On raspberrypi, "bringup" turtlebot3 and turn on the camera

   ```bash
   roslaunch turtlebot3_bringup turtlebot3_robot.launch
   roslaunch raspicam_node camerav2_410x308_30fps.launch
   ```

5. Turn on the ArUco finder

   ```bash
   cd ~/catkin_ws/src/aruco-ros
   roslaunch aruco_marker_finder.launch
   ```

6. Run the car

   ```bash
   roslaunch line_follower_turtlebot lf.launch
   ```

7. Till now the car should be able to run follow the black line and park in front of ArUco marker. To stop the car, except terminate at each terminators, a command is also needed to let the car stop

   ```bash
   rostopic pub /cmd_vel geometry_msgs/Twist "linear:
     x: 0.0
     y: 0.0
     z: 0.0
   angular:
     x: 0.0
     y: 0.0
     z: 0.0"
   ```

   <video id="video" controls="" src="runpark.mp4" preload="none">
</video>
