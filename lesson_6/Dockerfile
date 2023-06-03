FROM ubuntu:18.04
RUN apt update -y
RUN apt install default-jdk -y && \
    apt install tomcat9 && \
    apt install maven && \
    apt install git && \
    git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git && \
    mvn package /boxfuse-sample-java-war-hello/