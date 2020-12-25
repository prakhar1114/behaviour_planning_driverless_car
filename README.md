# Introduction
In this project, we make use of CARLA simulator to implement motion planning of self driving cars.

## Implementing the Motion Planner
Here, we make use of finite state machine to handle the scenario of stopping the car at a stop sign. It switches between 3 states, Follow Trajectory, Decelerate To Stop and Stay Stopped. It switches between states based on ego state.
Within the Follow Trajectory state of the finite state machine, the module implements path generation. It sets up and solves an optimization problem to develop a local trajectory between current position and some specified distance ahead (eg. 8m). It then makes use of conformal lattice planning to generate local possible paths and selects an optimal path for traversal. The path selection ensures that the chosen path is collision free and close to the trajectory centreline. Collision check is done by approximating the car by circles. It then generates a velocity profile for the generated path. Finally, the position and velocity data is passed to the vehicle motion controller module where the steering input, brakes and throttle is set by using a Pure Pursuit controller.

## Running the code
* Run the CARLA Simulator
* Open a new terminal. Change to the folder which contains this folder 'Python Client/Course4FinalProject'. Then write the following code in the terminal.
```
python3 module_7.py
```
