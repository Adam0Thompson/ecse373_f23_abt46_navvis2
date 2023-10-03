# Navvis 2 package description

## Overview
This package will open and display the contents of a bag file generated for the navvis robot in exploring the 5th floor of CWRU's Glennan building. In conjunction with navvis_description and maps_glennan packages, this package can display an accurate floorplan through rviz.


## How to use
This package contains 3 different launch files. Each run at default should provide sufficient results
### display_old.launch
This is the slightly edited launch file from last lab. Changes made were to account for misunderstandings i had with the lab 2 instructions, and do not alter the overall function of the launch file. This launch file takes 5 arguments, all are optional:
- use_xacro: can be set to true or false. If true, it will use the xacro version of the urdf file. if false, it will use the urdf generate file from the xacro version.
- use_joint_state_publisher_gui: toggles whether or not the joint_state_publisher_gui node will run. Either way join_state_publisher will run.
- use_robot_state_publisher: toggles the use of robot state publisher
- rviz_config_file: default set to config_old.rviz, but can be changed to any config file.
- file: change the xacro/urdf file that will be used

### display.launch
This launch file sets up the lasers on the robot, and preps to demonstrate the functionality of the bag. This launch file includes display_old.launch, and sets all arguments necessary. Additionally, this launch file has 3 arguments, all optional:
- use_external_time: toggles whether or not /use_sim_time:=true is passed into the rviz config file
- config_file: allows the user to specify a config file to use. default is config.rviz

### display_map.launch
This launch file includes display.launch and passes all necessary arguments into it. This launch file takes no new arguments, and sets up the bag reader, as well as launches the map_server.

## Notes from the author
The one thing that im still unsure of, is that the wheels do not move with the robot when the bag is running on the map. Im sure this is an easy fix, i just havent been able to figure out what it is.