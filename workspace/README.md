# Creating a catkin workspace
The next step is to create a *catkin workspace*. A catkin workspace is a folder directory in which you can create and modify existing packages. 

A catkin workspace can contains of *build*, *devel*, and *src* folders and each has different roles in the development process. 

First, let's create our workspace as `catkin_ws` and *src* folder in it:

> ```
> $ mkdir -p catkin_ws/src
> $ cd catkin_ws/src
> $ catkin_init_workspace
> ```

After entering above commands, only`CMakeLists.txt` created in the workspace. 
Now you can build the workspace by entering the following command:

> ```
> $ cd
> $ cd catkin_ws
> $ catkin_make
> ```

`catkin_make` command is a tool for working with *catkin workspace*. After building, you may noticed `build` and `devel` folders in *catkin_ws*. In `devel` folder, there are now several setup *.sh* files. We will source the setup.bash file to overlay this workspace on top of your ROS environment:

> ```
> $ cd
> $ cd catkin_ws
> $ source devel/setup.bash
> ```
You can check if the workspace properly overlayed using the following command:
> ```
> $ echo $ROS_PACKAGE_PATH
> /home/user_name/catkin_ws/src:/opt/ros/kinetic/share
> ```
