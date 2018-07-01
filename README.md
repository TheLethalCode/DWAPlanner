# DWAPlanner

Dynamic Window Approach is a local path planning algorithm which takes into account the kinodynamic constraints of the robot while generating a trajectory to the given destination point. 

## Algorithm

The robot generates a window of possible velocities and yaw-rate. With every velocity and yaw-rate in this window approximated to the required resolution, a trajectory is generated for a fixed interval in steps of a very small time interval (dt). Then all the trajectories that collide with an obstacle or go close to an obstacle with a speed that cannot be stopped are rejected. The remaining set of velocities and yaw-rate are the admissible set.

Of all the remaining trajectories, the best one is chosen with the help of an optimising function, which considers the proximity to an obstacle, progress towards the goal, time constraints, etc. This process is repeated for every interval of dt untill the robot reavhes the destination.

## Dependencies

Requires OpenCV (tested with 3.2)

## Running 

After cloning the repo, generate the executable with the help of a Makefile provided

`make New`

An object file will be generated. 

Then feed the cost map of the region, with obstacles marked as white, the starting marked in green, the destination in red and the rest of the region in black to the object file.

`./New a.png`

You should get the path generated from the start to the end.

To get optimal results, play with the parameters at the start of the New.cpp