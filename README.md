# ROAR ROS2 Parent Repository
<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">Table of Contents</h2></summary>
  <ol>
    <li>
      <a href="#about-the-package">About The Package</a>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#Usage">Usage</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>



<!-- ABOUT THE Package -->
## About The Package

This is a repository that contains all the packages for roar ros2 as seperate submodules.

<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these simple steps.

### A. Prerequisites

It is assumed that your system(s) is running Ubuntu 20.04 and has a working installation of ROS2 (Foxy). This repo has not been tested on other Operating Systems.

Please follow instructions on how to install [ROS Foxy](https://docs.ros.org/en/foxy/Installation.html)



### B. Installation

1. Clone the repository and its dependencies.
    ```bash
    git clone --recurse-submodules https://github.com/amansrf/roar_ros.git
    ```
2. Install required ROS packages from inside the roar_ros folder.
    ```bash
    cd roar_ros
    sudo apt-get update
    sudo rosdep init
    rosdep update
    rosdep install -i --from-path src --rosdistro foxy -y
    ```
3. Build all the packages and source the workspace
    ```bash
    colcon build --symlink-install
    source <path_to_roar_ros>/install/setup.bash
    ```

<!-- LICENSE -->
<!-- ## License
Distributed under the MIT License. See `LICENSE` for more information. -->

<!-- USAGE -->
## Usage

1. Launch the iphone app and calibrate it with world centre.
2. Change the ip address of the iphone in the config.py file located at: ```roar_ros/src/ros_roar_streamer/ros_roar_streamer/config.py```
3. Run the ros_roar_streamer state_streamer node:
    ```bash
    ros2 run ros_roar_streamer state_streamer
    ```
4. Run the transforms package in a new terminal:
    ```bash
    source <path_to_roar_ros>/install/setup.bash
    ros2 launch roar_transforms roar_tf.launch.py
    ```
5. Run the roar_bot_description package in a new terminal:
    ```bash
    source <path_to_roar_ros>/install/setup.bash
    ros2 launch roar_bot_description display.launch.py
    ```

<!-- CONTACT -->
## Contact
If you have any issues or find any bugs please feel free to contact:

Aman Saraf     - amansaraf99@gmail.com, aman_saraf@berkeley.edu


<!-- ACKNOWLEDGEMENTS -->
<!-- ## Acknowledgements and References

TO DO -->