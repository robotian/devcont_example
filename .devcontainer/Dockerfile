FROM osrf/ros:humble-desktop

ARG USERNAME=robotian
ARG USER_UID=1000
ARG USER_GID=$USER_UID
ARG DEBIAN_FRONTEND=noninteractive


RUN groupadd --gid $USER_GID $USERNAME \
  && useradd -s /bin/bash --uid $USER_UID --gid $USER_GID -m $USERNAME \
  && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
  && chmod 0440 /etc/sudoers.d/$USERNAME 
  

# Switch to our new user
USER $USERNAME
ENV USER=$USERNAME

# Set up the environment
WORKDIR /home/$USERNAME
RUN echo "source /opt/ros/humble/setup.bash" >> /home/$USERNAME/.bashrc
