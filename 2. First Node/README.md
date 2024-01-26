# Create Your first ROS2 Node using python

## Creating a workspace

Let us start by creating a workspace for ROS2

Create a directory with the name of your choice. Following the convention, I will name the workspace ros2_ws.
```
mkdir ros2_ws
cd ros2_ws
```

Create a src directory inside the newly created directory. This is where all the source code files and packages will be present

```
mkdir src
```

Build your workspace using colcon build

```
colcon build
```
This should result in a successful build resulting in the following output
```
Summary: 0 packages finished [2.79s]
```
and the following files should be present in your workspace directory

```
~/ros2_ws$ ls
build  install  log  src
```
Inside the install directory, You will find the local_setup.bash and setup.bash files,
To activate the local setup:
```
source /home/tejas/ros2_ws/install/local_setup.bash
#modify as per the path in your local directory
```
You can add them to your .bashrc file depending on your requirements.


## Creating a python Package

To create a ROS2 node, You will need to create a package.
Move to the src directory in your workspace
```
cd src
```
Here, you can use the following command to create a new package (lets call it test_pkg)
```
ros2 pkg create test_pkg
```
You can also specify its build type and dependencies so that the package can be built accordingly

```
ros2 pkg create test_pkg --build-type ament_python --dependencies rclpy
```
rclpy is the python distribution for ROS2

To build your package, simply move to its directory and perform:
```
colcon build
```





