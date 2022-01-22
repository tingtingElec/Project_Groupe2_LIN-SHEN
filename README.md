# Project_Groupe2_LIN-SHEN
Final project-Indoor real-time navigation for robot vehicles  
All the packages we  

- hector_slam
- navigation
- rplidar_ros
- 
$cd catkin_ws/src

$git clone the package you need from the internet
$cd ~/catkin_ws && catkin_make
$source ~/catkin_ws/devel/setup.bash
Record Indoor Map with Rplidar
$roscore
launch new terminal
$roslaunch rplidar_ros rplidar.launch
launch new terminal
$roslaunch hector_slam_launch tutorial.launch
launch new terminal
$rosrun map_server map_saver -f  map_name
Turtlebot Simulation With Indoor map
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
launch new terminal
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml
Remote Control TurtleBot3
ssh pi@172.20.10.12
password:980723
On Remote PC Virtual Machine
(Parallels Desktop Change Sharing mode to Bridge mode,not for other virtual machines)
$ifconfig 
IP address:172.20.10.3
$nano ~/.bashrc
export ROS_MASTER_URI=http://172.20.10.3:11311
export ROS_HOSTNAME=172.20.10.3
After changing,save and validate
$source ~/.bashrc
On Raspberry
$nano ~/.bashrc

export ROS_MASTER_URI=http://172.20.10.3:11311
export ROS_HOSTNAME=172.20.10.12
After changing,save and validate
$source ~/.bashrc
Remote Control on remote PC
$roscore
launch new terminal
$ssh pi@172.20.10.12
password:980723
$roslaunch turtlebot3_bringup turtlebot3_robot.launch
launch new terminal
$export TURTLEBOT3_MODEL=burger
(For Teleoperation)
$roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
(For Navigation)
$roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml  
