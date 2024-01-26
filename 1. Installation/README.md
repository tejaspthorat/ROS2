## Install ROS2 Humble for Ubuntu 22.04

### Visit https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html for updated installation instructions

### Step 1: Ensure UTF-8 Locale
Make sure you have a locale that supports UTF-8
```
locale  # check for UTF-8
```
If the locale is UTF-8, You should see the following output and you are good to proceed with the installation

```
LANG=en_US.UTF-8
LANGUAGE=en_IN:en
LC_CTYPE="en_US.UTF-8"
LC_NUMERIC="en_US.UTF-8"
LC_TIME="en_US.UTF-8"
LC_COLLATE="en_US.UTF-8"
LC_MONETARY="en_US.UTF-8"
LC_MESSAGES="en_US.UTF-8"
LC_PAPER="en_US.UTF-8"
LC_NAME="en_US.UTF-8"
LC_ADDRESS="en_US.UTF-8"
LC_TELEPHONE="en_US.UTF-8"
LC_MEASUREMENT="en_US.UTF-8"
LC_IDENTIFICATION="en_US.UTF-8"
LC_ALL=en_US.UTF-8
```

If not, follow the below steps to switch to a UTF-8 Locale

```
sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings

```

### Step 2: Setup resources
First, ensure that the Ubuntu Universe repository is enabled.

```
sudo apt install software-properties-common
sudo add-apt-repository universe
```

Now add the ROS 2 GPG key with apt

```
sudo apt update && sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
```

Then add the repository to your sources list.

```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```

### Step 3: Install ROS2 Packages

```
sudo apt update
```
ROS 2 packages are built on frequently updated Ubuntu systems. It is always recommended that you ensure your system is up to date before installing new packages.
```
sudo apt upgrade
```
Download any one of the following based on your requirements:

Desktop Install (Recommended): ROS, RViz, demos, tutorials.

```
sudo apt install ros-humble-desktop
```

ROS-Base Install (Bare Bones): Communication libraries, message packages, command line tools. No GUI tools.

```
sudo apt install ros-humble-ros-base
```
Download the required dev tools:

```
sudo apt install ros-dev-tools
```

### Step 4: Environment Setup
Set up your environment by sourcing the following file.

```
source /opt/ros/humble/setup.bash
```

Add it to the end your .bashrc file so that it runs everytime you open a new terminal

### Step 5: Try out some of the examples

In one terminal, source the setup file and then run a C++ talker:
```
ros2 run demo_nodes_cpp talker
```

In another terminal source the setup file and then run a Python listener:

```
ros2 run demo_nodes_py listener
```

Running Example:

![Screenshot from 2024-01-26 12-43-24](https://github.com/tejaspthorat/ROS2/assets/97504422/73e95ee2-6a70-405b-8744-f9178ca3df02)

