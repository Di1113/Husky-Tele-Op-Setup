# Husky Tele-op Setup with ROS1 Noetic
###### Author: Shrijit Singh (shrijits), Di Hu (yudanh)
###### Last edited: 05/23/2022

<br>

### Setup the logitech joystick controller for Husky

1. Export these environment variables in bashrc or zshrc to make it support logitech controller 

```
# ROS1 Husky Joystick Config
export HUSKY_LOGITECH=1
export HUSKY_JOY_DEVICE="/dev/input/f710"
```

ref: https://github.com/spraybot/dotfiles/blob/master/.config/zsh/spraybot.zsh

<br>

2. Run the following command to rename and connect to the controller usb port

```
sudo wget https://raw.githubusercontent.com/spraybot/spraybot_tools/main/udev/90-clearpath.rules -P /etc/udev/rules.d/
```

ref: https://github.com/spraybot/spraybot_tools/wiki/Udev-Rules 

(the joystick configuration starts to take effect in a new terminal window)
<br><br>

### Setup software packages 

3. Create a catkin ws and clone this repo into the ws 

repo: https://github.com/husky/husky_robot

PS: Select the noetic-devel version to clone.

<br>

4. Install extra packages required:

```
sudo apt install "ros-noetic-husky-*" and whatever packages are missing
```

<br>

5. Build and source catkin-ws

<br>

6. Run roslaunch command 

```
roslaunch husky_base base.launch
```
(will launch file: https://github.com/husky/husky_robot/blob/noetic-devel/husky_base/launch/base.launch)
