#https://github.com/athackst/dockerfiles
FROM althack/ros:noetic-gazebo

RUN apt-get update \
 && apt-get install -y -qq --no-install-recommends \
  libglvnd0 \
  libgl1 \
  libglx0 \
  libegl1 \
  libxext6 \
  libx11-6

# Env vars for the nvidia-container-runtime
ENV NVIDIA_VISIBLE_DEVICES all
ENV NVIDIA_DRIVER_CAPABILITIES graphics,utility,compute
ENV QT_X11_NO_MITSHM 1

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update \
   && apt-get -y install \
   ros-$ROS_DISTRO-desktop-full \
   ros-$ROS_DISTRO-kobuki-driver \
   ros-$ROS_DISTRO-gmapping \
   ros-$ROS_DISTRO-dwa-local-planner \
   ros-$ROS_DISTRO-ros-control \
   ros-$ROS_DISTRO-ros-controllers \
   ros-$ROS_DISTRO-pid \
   ros-$ROS_DISTRO-urg-node \
   ros-$ROS_DISTRO-joy-* \
   ros-$ROS_DISTRO-laser-* \
   ros-$ROS_DISTRO-ecl-* \
   # ros-$ROS_DISTRO-yocs-controllers \
   ros-$ROS_DISTRO-joint-state-controller \
   ros-$ROS_DISTRO-move-base \
   ros-$ROS_DISTRO-urdf-sim-tutorial \
   # Clean up
   && apt-get autoremove -y \
   && apt-get clean -y \
   && rm -rf /var/lib/apt/lists/*
ENV DEBIAN_FRONTEND=

# Set up auto-source of workspace for ros user
ARG WORKSPACE
RUN echo "if [ -f ${WORKSPACE}/devel/setup.bash ]; then source ${WORKSPACE}/devel/setup.bash; fi" >> /home/ros/.bashrc
RUN echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
