# Control-RX200-with-python-demos-and-MoveIt
This repository includes step-by-step controlling of the RX200 arm using the Trossen Python demos and moveIt.

## Launch the real RX200 arm in MoveIt using the following command:

Open new Terminal

$ source ~/interbotix_ws/devel/setup.bash

$ roslaunch interbotix_xsarm_moveit_interface xsarm_moveit_interface.launch robot_model:=rx200 use_actual:=true

I got this error "[ERROR] [1708450203.679839683]: Exception while loading planner 'ompl_interface/OMPLPlanner': According to the loaded plugin descriptions the class ompl_interface/OMPLPlanner with base class type planning_interface::PlannerManager does not exist. Declared types are 
Available plugins:"

This error was solved by installing moveit for melodic

$ sudo apt-get install ros-melodic-moveit

We have two gropus: interbotix_arm and interbotix_gripper. We tested different goal state such as "Home" for "interbotix_arm" and "closed" for "interbotix_gripper".

Now, we will test the available python demos. Remember to set goal state to "sleep" before closing the "moveit" node.

## Launch the real RX200 and control it using the Trossen python demos:
Open new Terminal

$ source ~/interbotix_ws/devel/setup.bash

$ roslaunch interbotix_xsarm_control xsarm_control.launch robot_model:=rx200

Navigate to the folder of python_demos using the following command

$ cd ~/interbotix_ws/src/interbotix_ros_manipulators/interbotix_ros_xsarms/examples/python_demos

 We will test "ee_cartesian_trajectory.py" by running the following command

 You need to change the robot model to "rx200" in the first line 

 "bot = InterbotixManipulatorXS("rx200", "arm", "gripper")"

 $ python ee_cartesian_trajectory.py

I got this error "ImportError: dynamic module does not define module export function (PyInit__tf2)"

I solved it by creating anaconda virtual environment using the following steps and run the python file again:

 $ conda create --name ros_env python=2.7
 
 $ conda activate ros_env

 $ pip install pyyaml

 $  pip install rospkg

 $  pip install numpy 2043  pip install modern-robotics

 Run the python code again and it works
 
 $  python ee_cartesian_trajectory.py

