# Inistall-Ros-steps (Task 1)
First of all Download VM VirtualBox, then Install.

Download ubuntu 20.04.4 64bit. "http://wiki.ros.org/noetic/Installation/Ubuntu"

Start Configure your Ubuntu repositories 
for ROS " http://packages.ros.org/ros/ubuntu "


![لقطة الشاشة  ](https://user-images.githubusercontent.com/86748540/181916260-65b8b8c1-4825-4295-9e4f-6982c335f716.png)


Configuration
```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```

Set up keys
```bash
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```


Install

```bash
sudo apt update
```


for desktop Install

```bash
sudo apt install ros-noetic-desktop-full
```

Environment setup


```bash
source /opt/ros/noetic/setup.bash
```
```bash
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
```
```bash
gedit~/.bashrc
```

#Taks 2

installing ROS2 into Jetson nano

Installation steps

1. Set locale Make sure that we have locale supports UTF-8
locale
sudo apt update && sudo apt install locales sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

2. Setup the sources apt-cache policy | grep universe 
3. Enable the Universe repository with the instructions. sudo apt install software-properties-common sudo add-apt-repository universe 
4. Add ROS2 repository to the system sudo apt update && sudo apt install curl gnupg2 lsb-release sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg 
5. Add the repository to the sources list echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(source /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null 
6. Install ROS 2 packages update the apt repository

sudo apt update upgrade

sudo apt upgrade Desktop Install: ROS, RViz, demos, tutorials. sudo apt install ros-foxy-desktop ROS-Base Install (Bare Bones): Communication libraries, message packages, command line tools. No GUI tools. sudo apt install ros-foxy-ros-base 7. Setup the enviroment Bash echo "source /opt/ros/foxy/setup.bash" >> ~/.bashrc source ~/.bashrc Zsh echo "source /opt/ros/foxy/setup.zsh" >> ~/.zshrc source ~/.zshrc
