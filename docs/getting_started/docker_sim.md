# Docker Simulation Tutorial

## Setup SSH keys on Host

* Ensure that you have setup ssh keys on your host computer to be able to clone the CogniPilot repositories: [Connecting to GitHub with SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

## Setup Docker

* Install the offfical Docker package: [Docker Setup](https://github.com/CogniPilot/docker)

```bash
git clone git@github.com:CogniPilot/docker
cd docker/dream
./run.sh terminator
```

## Setup Helmet for MrBuggy3 SITL

```bash
cd ~/work
git clone git@github.com:CogniPilot/helmet
vcs import < helmet/dream/base.yaml
vcs import < helmet/dream/mrbuggy3.yaml 
```

## Build Cranium

```bash
cd ~/work/cranium
colcon build --symlink-install
. ./install.setup.sh
```

## Build Cerebri MrBuggy3 SITL

```bash
cd ~/work/ws/cerebri
west init -l .
west update
west build app/mrbuggy3/ -b native_posix -t install -p
```

## Run MrBuggy3 SITL

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

![MRBuggy3 Depot world simulation.](data/mrbuggy3_depot.png "MRBuggy3 Depot world simulation")

!!! attention
    **Use a joystick controller (logitech F310 suggested) to control vehicle modes.**

## Select a Mode:

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


