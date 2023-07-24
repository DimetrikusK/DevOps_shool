FROM ubuntu:18.04

RUN apt-get update -y && \
    apt-get install wget -y && \
    apt-get install curl -y && \
    apt-get install dpkg -y &&\
    apt-get install -y gpg

#install java
RUN apt-get install default-jdk -y

#install maven
RUN apt-get install maven -y
#RUN wget wget http://www-eu.apache.org/dist/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz && \
#    tar -zxvf apache-maven-3.3.9-bin.tar.gz  && \
#    mv apache-maven-3.3.9 /opt/

#install docker
RUN for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do apt-get remove $pkg; done
RUN install -m 0755 -d /etc/apt/keyrings
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg
RUN chmod a+r /etc/apt/keyrings/docker.gpg
RUN echo \
      "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
      "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
      tee /etc/apt/sources.list.d/docker.list > /dev/null
RUN apt-get update -y
RUN apt-get install docker.io -y
