# Morris_data_collection

## Start the shepherd rover 
You will need three tabs in the terminal for this
1. ```$ roslaunch rr_openrover_basic example.launch ```
2. ```$ sudo rmmod xpad && sudo xboxdrv```
Then turn on the xbox controller to see if you could see command in the terminal. If yes, the xbox controller is correctly setup.
3. ```$ roslaunch rr_control_input_manager example.launch```
If the first or the third step failed, try unplug and pulg the usb hub. Without errors, you should be able to control the rover with the xbox controller.

## Start the GPS service and record in ros
1. ``` $ roslaunch piksi_multi_rtk_ros piksi_multi_rover_shepherd_duro.launch```
2. echo the rostopic to make sure the GPS initialized correctly ``` $ rostopic echo /piksi_duro_tcp/enu_pose_best_fix```
 

## Start realsense and record in ROS
1. ``` $ roslaunch realsense2_camera rs_camera.launch```
2. Record all the rostopics ``` $ rosbag record -o /mnt/sda1/morris -a``` This command will add a timestamp to the .bag name such that it will not overwrite other .bag files

## Drive the rover into the corn field
Find two types of corn rows, one relatively in the middle where sunlight is relatively dimmed, and one relatively outside. Drive the rover straight in until the end and straight out.
