# DWAPlanner

This package integrates the Dynamic Window Approach with Robot Operating System by providing a node has an interface. DWA is a local planner which generates a trajectory considering the kinodynamic constraints of the bot when peovided with the intermediate goal waypoints to the ultimate destination. 

Here the node subscribes to the belief from the *odometry/filtered* topic which is assumed to be an accurate estimation of the robot's pose. It then generates a trajectory for the robot to follow and publishes the commands to the *cmd_vel* topic.

To get the costmap, it subscribes to the *map* topic and for the goal, it subscribes to the *goal* topic.

There are various parameters, which are suitable for different robots and surroundings. Configure these parameters in the .yaml file to get the most optimal results.

This package is in development status and bugs and bug fixes are welcome.

## Running the package

Clone the repo into your catkin workspace: ` git clone https://github.com/TheLethalCode/DWAPlanner.git` 

Catkin_make your workspace: ` catkin_make`

Then ros launch the node: ` roslaunch DWA dwa_launch.launch`

Now run a bag file or run the node in your robot and get the path in *cmd_vel* topic.