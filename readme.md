## ROS Remote Teleop

This repository contains a barebones implementation of remote teleoperation of a ROS-based robot over the internet by using ROSlib. We create an HTTP server on the robot and run a rosnode on this server to publish and subscribe to relevant topics (e.g., image observations and control commands). Accessing this web server from other machines (non-ROS machines, mobile browser etc.) enables remotely controlling the robot over the internet.


### Pre-Requisites

- ROS (tested on kinetic)
- Python packages: http
- JavaScript


### How to Run

Launch multiple terminals/tmux/screen to run these processes independently. This assumes that the ROS master and other robot processes are already running. `index.html` has an example image subscriber and control publisher. Please fill the placeholders for the IP and ROS topic names in `index.html`.

#### 1.
`python -m http.server <desired_port>`

#### 2.
`roslaunch rosbridge_server rosbridge_websocket.launch`

#### 3. On Remote Device
Launch a web browser (tested with Safari, Chrome, Firefox) and navigate to `<robot_ip_address:desired_port>`




<img src="assets/teleop.gif" width=75%/>
