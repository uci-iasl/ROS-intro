# Creating, Building and Cloning packages

So far, we have [installed ROS](https://github.com/dcallega/ROS_Batbold_experience/tree/master/Installation), created and built a [workspace](https://github.com/dcallega/ROS_Batbold_experience/tree/master/workspace). Now in this section, we will clone packages from online resources such as GitHub and create our own package. 

### git installing

First of all, to clone repositories from GitHub, you are going to need git commands. To install `git`, type the following command line in terminal: 
>```sh 
>$ sudo apt-get install git
>```
## Cloning repositories

First, let's clone the package in our catkin workspace:
>```sh 
>$ cd catkin_ws/src
>$ git clone https://github.com/<repositories_name>.git -b <branch_name>-devel
>$ cd ..
>$ rosdep install --from-paths src -i
>$ catkin_make
>```

## Creating packages

First change to the source space directory of the catkin workspace you created in the [Creating a Workspace](https://github.com/dcallega/ROS_Batbold_experience/tree/master/workspace): 
>```sh 
>$ cd catkin_ws/src
>```
Now use the `catkin_create_pkg` script to create a new package. catkin_create_pkg requires that you give it a package_name and optionally a list of dependencies on which that package depends: 
>```sh 
>$ catkin_create_pkg <package_name> [depend1] [depend2] [depend3]
>```

*Example:*

>```sh 
>$ catkin_create_pkg beginner_tutorials std_msgs rospy roscpp
>```
The newly created package, beginner_tutorials, contains a *package.xml* and a *CMakeList.txt*, which have been partially filled out with the information using *catkin_create_pkg*.

## Building a catkin workspace and sourcing the setup file

Now you need to build the packages in the catkin workspace: 

>```sh 
>$ cd catkin_ws/src
>$ catkin_make
>```

After the workspace has been built it has created a similar structure in the devel subfolder as you usually find under */opt/ros/kinetic*. 
To add the workspace to your ROS environment you need to source the generated setup file:
>```sh
>$ . catkin_ws/devel/setup.bash
>```
