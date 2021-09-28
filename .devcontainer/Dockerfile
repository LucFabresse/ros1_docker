#https://github.com/athackst/dockerfiles
FROM althack/ros:melodic-gazebo

# RUN apt-get update \
#  && apt-get install -y -qq --no-install-recommends \
#   libglvnd0 \
#   libgl1 \
#   libglx0 \
#   libegl1 \
#   libxext6 \
#   libx11-6

# Env vars for the nvidia-container-runtime.
ENV NVIDIA_VISIBLE_DEVICES all
ENV NVIDIA_DRIVER_CAPABILITIES graphics,utility,compute
ENV QT_X11_NO_MITSHM 1

# ** [Optional] Uncomment this section to install additional packages. **

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update \
   && apt-get -y install ros-melodic-desktop-full \
   ros-melodic-kobuki-driver \
   ros-melodic-gmapping \
   ros-melodic-dwa-local-planner \
   ros-melodic-ros-control \
   ros-melodic-ros-controllers \
   ros-melodic-pid \
   ros-melodic-urg-node \
   ros-melodic-joy-* \
   ros-melodic-laser-* \
   ros-melodic-ecl-* \
   ros-melodic-yocs-controllers \
   ros-melodic-joint-state-controller \
   ros-melodic-move-base \
   ros-melodic-pr2-move-base \
   ros-melodic-pr2-description \
   ros-melodic-urdf-sim-tutorial \
   # Clean up
   && apt-get autoremove -y \
   && apt-get clean -y \
   && rm -rf /var/lib/apt/lists/*
ENV DEBIAN_FRONTEND=dialog

ARG WORKSPACE

# Set up auto-source of workspace for ros user
ARG WORKSPACE
RUN echo "if [ -f ${WORKSPACE}/devel/setup.bash ]; then source ${WORKSPACE}/devel/setup.bash; fi" >> /home/ros/.bashrc
RUN echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
