## CMPUT 412 Winter 2018 Competition 1: Pursuit & Evasion, By Jae-yeon (Leo) Yoon and Sumeyye Aydin ##

The competition report can be found ![here](https://github.com/leoyoon17/CMPUT-412-Competition-1/blob/master/docs/report.md)!

To download the necessary files:
```
git clone https://github.com/leoyoon17/CMPUT-412-Competition-1

```
Note: Don't forget to connect the usb cables from the Kobuki base, the
Asus Xtion Pro Live, and the logitech controller to your computer! (or ssh)

Note: This program does not have a launch file as Leo's computer was unable to create a workspace package with "catkin_make", thus launchfiles would not run properly.

To run the pursuit program, first open 5 terminals (or tmux windows, etc):
===========================================================================

On the first terminal:
* $ roscore

On the second terminal:
* $ roslaunch turtlebot_bringup minimal.launch

On the third terminal:
* $ roslaunch turtlebot_bringup 3dsensor.launch

On the fourth terminal:
* $ roslaunch turtlebot_teleop logitech.launch

On the fifth terminal:
* change directory to /Competition 1/CMPUT-412-Competition-1/src/followbot
* ./follower.py cmd_vel:=cmd_vel_mux/input/teleop

* Finally, press the 'X' button on the logitech controller to start or stop the program!


To run the evasion program, again, open 5 terminals (or tmux windows, etc):
=======================================================================

On the first terminal:
* $ roscore

On the second terminal:
* $ roslaunch turtlebot_bringup minimal.launch

On the third terminal:
* $ roslaunch turtlebot_bringup 3dsensor.launch

On the fourth terminal:
* $ roslaunch turtlebot_teleop logitech.launch

On the fifth terminal:
* change directory to /Competition 1/CMPUT-412-Competition-1/src/evadebot
* $ ./wander.py cmd_vel:=cmd_vel_mux/input/teleop

* Finally, press the 'X' button on the logitech controller to start or stop the program!





