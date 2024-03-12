# Setup scripts for ROS2, Gazebo, Rove and Docker

These scripts are partly based on the Dockerfile found in the Rove repo.
They also retain their progress if they fail or are aborted by the user.

This has been tested on a clean install of Ubuntu 22.04 with 8G of RAM and 8G of swap (simply having 8G of RAM wasn't enough to build the workspace).
See [this](https://linuxize.com/post/create-a-linux-swap-file/) for info on how to setup a swapfile if needed.

## Usage:
Run the scripts with no parameters to continue execution from last checkpoint (starts at 0 if first time run or if it was previously completed).

To force execution to start at a given checkpoint, run with an integer parameter indicating the step number.

## setup_ros2
**Important notes:**

- Recommended at least 12G of memory/swap (only 8G of RAM and 0G swap would freeze Ubuntu while building)
- Partway through the script you will be prompted to **source ROS 2**
- If you are using zsh instead of bash, make sure to modify the second to last step
- You can install any ROS 2 distro by changing the value of `$DEVEL`

This script will install a few things:

- ROS 2 `humble` (this can be changed to any other devel by changing `$DEVEL`)
- Rove
- Gazebo

This script will also build the workspace. Rove will be installed in `~/capra_ws`.

## setup_docker
This script will install docker.

> Simple as that