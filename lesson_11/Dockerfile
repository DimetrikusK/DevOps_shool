FROM openjdk:11

RUN apt-get update -y && \
    apt-get upgrade -y

#install maven
RUN wget https://mirrors.estointernet.in/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz && \
    tar -xvf apache-maven-3.6.3-bin.tar.gz && \
    mv apache-maven-3.6.3 /opt/

#install docker
RUN apt-get install docker-ce

#clear cache
RUN apt-get clean