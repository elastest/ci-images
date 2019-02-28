##########################
#
# Docker file to  extend elastest/docker-siblings:latest with
#     - git
#     - git-lfs
#     - netcat
#
########################

FROM elastest/ci-docker-siblings:latest

LABEL maintainer="gtunon@naevatec.com"

# user for setting the environment
USER root

## git
RUN apt-get -y install git

## git
RUN curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | bash
RUN apt-get -y install git-lfs

## install python 3 and pip3
RUN apt-get install -y python3
RUN apt-get install -y python3-pip


## Git Large File Storage (LFS) support
RUN git lfs install

## netcat
RUN apt-get -y install netcat

# set envs
ENV WORKSPACE /home/jenkins

USER jenkins

WORKDIR ${WORKSPACE}

# launch container
#ENTRYPOINT ["/bin/bash"]
