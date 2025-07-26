# SAV_DOMPC

This project aims to enhance the control of the Soft Aerial Vehicle (SAV) during aerial grasping by using Disturbance Observer-based Nonlinear Model Predictive Control (DOMPC). By integrating a disturbance observer into the Nonlinear Model Predictive Control (NMPC) framework, we compensate for dynamic model idealizations and uncertainties arising from additional payloads and unpredictable disturbances. This approach effectively minimizes tracking errors and enables precise aerial grasping along all three axes.

## Installation 
The DOMPC in this project is a branch of the [airo_control_interface](https://github.com/HKPolyU-UAV/airo_control_interface.git) @ [AIRO-LAB](https://github.com/HKPolyU-UAV) @ RCUAS, HKPolyU.

Please refer to the instructions of the [airo_control_interface](https://github.com/HKPolyU-UAV/airo_control_interface.git).

## Parameters
[**ekf_observer_gazebo.yaml**](https://github.com/Athenachc/sav_dompc/blob/main/airo_control/config/gazebo/observer/ekf_observer_gazebo.yaml) and [**ekf_observer_vicon.yaml**](https://github.com/Athenachc/sav_dompc/blob/main/airo_control/config/vicon/observer/ekf_observer_vicon.yaml)
`r_pos_x`, `r_pos_y`, `r_pos_z`: Components of the measurement noise covariance matrix R corresponding to the measured x, y, and z positions, respectively.

`r_vel_x`, `r_vel_y`, `r_vel_z`: Components of the measurement noise covariance matrix R corresponding to the measured x, y, and z velocities, respectively.

`r_control_x`, `r_control_y`, `r_control_z`: Components of the measurement noise covariance matrix R corresponding to the measured x, y, and z disturbances, respectively.

`q_pos_x`, `q_pos_y`, `q_pos_z`: Components of the process noise covariance matrix Q corresponding to the predicted x, y, and z positions, respectively.

`q_vel_x`, `q_vel_y`, `q_vel_z`: Components of the process noise covariance matrix Q corresponding to the predicted x, y, and z velocities, respectively.

`q_disturbance_x`, `q_disturbance_y`, `q_disturbance_z`: Components of the process noise covariance matrix Q corresponding to the predicted x, y, and z disturbances, respectively.

## Demo in VICON

Connect to mavros
```
roslaunch airo_control mavros_vicon.launch
```

Open another terminal or tmux window (if using docker) to connect vrpn
```
roslaunch airo_control vrpn.launch
```

Open another terminal or tmux window (if using docker) to connect `airo_control_interface` with DOMPC
```
roslaunch airo_control fsm_vicon.launch
```

Open another terminal or tmux window (if using docker) to run a demo 
```
rosrun airo_control example_mission_node
```

## Soft Gripper Control and Fabrication
For details, please free feel to check this [repo](https://github.com/Athenachc/sav_gripper.git)


