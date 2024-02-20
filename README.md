# Control-RX200-with-python-demos-and-MoveIt
This repository includes step-by-step controlling of the RX200 arm using the Trossen Python demos and moveIt.

## Launch the real RX200 arm in MoveIt using the following command:

Open new Terminal

$ source ~/interbotix_ws/devel/setup.bash

$ roslaunch interbotix_xsarm_moveit_interface xsarm_moveit_interface.launch robot_model:=rx200 use_actual:=true
