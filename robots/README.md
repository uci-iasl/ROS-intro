# ROS with robots

In this section, I would like to introduce three robots I have used the most. These are 
* [Turtlebot](./turtlebot)
* [Husky Rover](./husky_rover)
* [Hector Quadrotor](./hector_quadrotor)

Using these robots, I will show how to move them by sending velocity using both commands and coding.

## Controlling robots using */cmd_vel* topic

To send velocity commands to robots througth topic `/cmd_vel`, which is of type `geometry_msgs/Twist`. A twist is composed of:
>```
> geometry_msgs/Vector3 linear
> geometry_msgs/Vector3 angular
>```
Therefore, it is specified by a linear velocity vector and an angular velocity vector.

To move the robot, first make sure that you have ran a *gazebo launch file*

*Example:*

>```sh
> $ roslaunch husky_gazebo husky_empty_world.launch
>```

### Using a command line to move robots

After launching *husky_empty_world.launch*, enter the following command line in new terminal:
>```sh
> $ rostopic pub /cmd_vel geometry_msgs/Twist '[1.0,0.0,0.0]' '[0.0, 0.0, 0.0]'
>```
It will publish a constant linear velocity of 1.0 m/s along the x-axis of the robot. In other word, the robot will go foward with the velocity of 1.0 m/s.

Next, the followng command line is used to rotate left with the angular velocity of 0.5 rad/s:
>```sh
> $ rostopic pub /cmd_vel geometry_msgs/Twist '[0.0,0.0,0.0]' '[0.0, 0.0,0.5]'
>```
Same as above two examples, you can move and rotate the robot along the y and z-axis.

In case of drones such as Hector quadrotor, drones can move in 3 dimensions. Therefore, I recommend to takeoff first and move it. 
(NOTE: when rotating, right hand rule is applied. +z turns left and -z turns left)

### Using a controller to move robots

The easiest method to controller is to use `teleop_twist_keyboard`, which can operate all robots I mentioned above (Turtlebot, Husky Rover, and Hector Quadrotor). 

To install `teleop_twist_keyboard`, we can just use install using a binary installation:

>```sh
> $ sudo apt-get install ros-kinetic-teleop-twist-keyboard
>```

And you can run it with the this command line:

>```sh
> $ rosrun teleop_twist_keyboard teleop_twist_keyboard.py
>```
