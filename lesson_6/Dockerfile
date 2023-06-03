FROM ubuntu:18.04
RUN apt update -y
RUN apt install default-jdk -y && \
    apt install tomcat9 -y && \
    apt install maven -y && \
    apt install git -y
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
RUN mvn package /boxfuse-sample-java-war-hello/