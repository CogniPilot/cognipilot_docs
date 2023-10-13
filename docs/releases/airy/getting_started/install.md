# Installation

## Requirements

* Ubuntu 22.04 host environment

This may work on other environments but only Ubuntu 22.04 is officially supported.

## Docker Option

If you wish, there is a development docker container ([docker hub](https://hub.docker.com/r/cognipilot/dream), [docker source](https://github.com/CogniPilot/docker)) for CogniPilot with Nvidia GPU support. If you use this option, do not run the native\_install script, as the packages are already installed.

## Setup SSH keys on Host and GitHub

* Ensure that you have setup ssh keys on your host computer and GitHub to be able to clone the CogniPilot repositories: [Connecting to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

## Setup GPG keys on Host and GitHub (Optional)

* Ensure that you have setup gpg keys on your host computer and GitHub to sign your commits: [Connecting to GitHub with SSH](https://docs.github.com/articles/generating-a-gpg-key/)

## Install Git

```bash
sudo apt install git
```

## Clone Helmet

```bash
mkdir -p ~/cognipilot
cd ~/cognipilot
git clone git@github.com:cognipilot/helmet
```

## Run Install Script (If not using docker)

```bash
~/cognipilot/helmet/install/native_install.sh
. ~/.profile
```

## SITL Convenience Script

```bash
build_mrbuggy3_sitl
```

This command is running the [following script](https://github.com/CogniPilot/helmet/blob/398e99d98c1a9aabef663ad601d3ac5c141b54f2/install/resources/build_mrbuggy3_sitl).

This script does the following:

 * Sets up the vcs workspaces based on yaml files provided in helmet.
 * Builds the cranium ROS 2 workspace
 * Builds Cerebri native\_posix software-in-the-loop simuliation
 * Builds Cyecca (control/estimation software)
 * Builds Electrode (ground station software)

```bash
```

## Start JupyterLab (if you want)

```bash
cyecca
```

## Run MrBuggy3 SITL (in JupyterLab terminal or Bash directly)

```bash
ros2 launch mrbuggy3_gz_bringup gz_nav2.launch.py
```

!!! attention
    **If running on a machine with a limited graphics card use:**
```bash
ros2 launch mrbuggy3_gz_bringup gz_nav2.launch.py world:=basic_map
```

## Simulation

Example of simulation running.

![MRBuggy3 Depot world simulation](data/mrbuggy3_depot.png "MRBuggy3 Depot world simulation")

!!! attention
    **Use a joystick controller ([Logitech F310](https://www.amazon.com/Logitech-940-000110-Gamepad-F310/dp/B003VAHYQY/) suggested) to control vehicle modes.**

## Select a Mode:

![F310](data/f310.jpg "F310")

* **A**: manual
* **X**: cmd_vel (nav2)
* **B**: auto (corti)

### Manual Mode:

* **Left stick** Up/Down: throttle
* **Right stick** Left/Right: steering

### Nav2 (cmd_vel) Mode:

* Click **2D Pose Goal** and select desired location on RVIZ2 map.

### Auto Mode

* Click **2D Pose Goal** and select desired location on RVIZ2 map.

## Arming

* **START**: arm
* **BACK**: disarm

