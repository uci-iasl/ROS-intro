# ROS setup

Despite ROS can run on MacOS and Windows, it is preferred to use Ubuntu to run ROS. ROS has different versions for every Ubuntu version (You can check which version you should install from [the link](http://wiki.ros.org/Distributions)). In my case, I am using ROS Kinetic, which runs on Ubuntu 16.04 LTS. In the rest of the tutorial, I will be using Ubuntu 16.04 and Ros Kinetic.


## Installing ROS Kinetic

Adding Source List
First step is to add the ROS repository address to ros-latest.list. Open a new terminal window and enter the following command.
> ```sh
> $ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
> ```

Setting up the Key
Now, we will add a public key to download the package from the ROS repository with the following command.
> ```
> $ sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
> ```
Installation
Before installing ROS using binary installation, make sure that your Debian package package is up-to-date by entering the command.
> ```sh
> $ sudo apt-get update
> ```
There are three versions of ROS versions for this installation depending on the usage and the need for the computer you are installing ROS on. But we will be using Desktop-Full, which consists of ROS, rqt, rviz, useful libraries, navigation, 2D and 3D simulators.
 
> ```sh
> $ sudo apt-get install ros-kinetic-desktop-full
> ```


Initialize rosdep
Be sure to initialize rosdep using ROS. The rosdep is a feature that improves convenience by easily installing dependent packages  when using or compiling core components of ROS.

> ```sh
> $ sudo rosdep init
> $ rosdep update
> ```

Environment Setup

It is convenient if the ROS environment variables are automatically added to your bash session every time a new shell is launched:

> ```sh
> $ echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
> $ source ~/.bashrc
> ```

Dependencies for building packages

Up to now you have installed what you need to run the core ROS packages. To create and manage your own ROS workspaces, there are various tools and requirements that are distributed separately. For example, rosinstall is a frequently used command-line tool that enables you to easily download many source trees for ROS packages with one command.

To install this tool and other dependencies for building ROS packages, run:
> ```sh
> $ sudo apt install python-rosinstall python-rosinstall-generator python-wstool build-essential
> ```

Installing Individual Package
We can also install a specific ROS package by entering the following command.
> ```sh
> $ sudo apt-get install ros-kinetic-PACKAGE
> ```

To find other ROS Kinetic package:
> ```sh
> $ apt-cache search ros-kinetic
> ```
