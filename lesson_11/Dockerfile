FROM ubuntu:20.04

# Update system
RUN apt-get update -y && \
    apt-get upgrade -y && \
    apt-get install openssh-server -y && \
    apt-get install wget -y && \
    apt-get install curl -y && \
    apt-get install dpkg -y &&\
    apt-get install -y gpg

# Install java
RUN apt-get update -y && \
    apt-get install default-jdk -y

# Install maven
RUN apt-get update -y && \
    apt-get install maven -y

# Install docker
RUN apt-get update -y && \
    apt-get install apt-transport-https ca-certificates curl software-properties-common -y && \
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add - && \
    add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" && \
    apt-get update -y && \
    apt-get install docker-ce -y

# Create user and copy ssh key
RUN useradd -ms /bin/bash jenkins && \
    usermod -aG sudo jenkins
WORKDIR /home/jenkins/.ssh
ADD id_rsa .
ADD /home/jenkins/.ssh/known_hosts home/jenkins/.ssh/known_hosts
RUN chmod 0700 /home/jenkins/.ssh && \
    chmod 600 /home/jenkins/.ssh/id_rsa && \
    chown -R jenkins:jenkins /home/jenkins