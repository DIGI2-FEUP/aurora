FROM public.ecr.aws/shadowrobot/ubuntu:bionic

LABEL Description="This image is used for testing empty Ubuntu Bionic deployment" Vendor="Shadow Robot" Version="1.0"

ENV DEBIAN_FRONTEND noninteractive
ENV LANG C.UTF-8
ENV USER testuser

RUN set -x && \
    apt-get update && \
    \
    echo "Installing sudo" && \
    apt-get install -y sudo && \
    \
    echo "Create testuser with empty password" && \
    useradd -m $USER && \
    passwd -d $USER && \
    adduser $USER sudo && \
    echo "$USER ALL=(ALL) NOPASSWD:ALL" | tee -a /etc/sudoers && \
    \
    echo "Clean up" && \
    apt-get clean && \
    rm -rf \
        /var/lib/apt/lists/* \
        /tmp/* \
        /var/tmp/* \
        /root/.ansible \
        /root/.gitconfig \
        /root/.cache

USER $USER
