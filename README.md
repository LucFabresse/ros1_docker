# What is it?

This repository gives a full Linux environment to locally develop in a dockerized ROS1 kinetic environnement with full access to GUI tools (rviz, gazebo, ...).

Special thanks to Allison Thackston for:
- [VSCode Template](https://github.com/athackst/vscode_ros2_workspace)
- [ROS Docker files](https://github.com/athackst/dockerfiles)
- [ROS Docker images](https://hub.docker.com/u/althack)

See [how she develops with vscode and ros2](https://www.allisonthackston.com/articles/vscode_docker_ros2.html) for a more in-depth look on how to use her workspace.


# Perequisites

* [docker](https://docs.docker.com/engine/install/)
* [nvidia-docker](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html)
* [vscode](https://code.visualstudio.com/)
* [vscode remote containers plugin](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

Tested on [Pop!_OS](https://pop.system76.com/) 21.04.

# How to use?

cf. https://github.com/athackst/vscode_ros2_workspace/blob/foxy/README.md

```
git clone https://github.com/LucFabresse/ros1_docker
code ros1_docker
# reopen in container...
# build the docker image
# opening a terminal in VSCode in now opened inside the docker container
```

# Rocker

[rocker](https://github.com/osrf/rocker) is a CLI tool to easily launch docker container with user rights, nvidia, ...

```
pip install rocker
rocker --x11 --nvidia --user --home --name ros2_dev althack/ros2:foxy-gazebo-nvidia bash
```

# To look at

- https://github.com/ceri-num/LARM-RDS-Simulation-WS
- https://github.com/albertodesouza/r2d2
- https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
- http://wiki.ros.org/turtlebot3_simulations

