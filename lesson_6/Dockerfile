#FROM ubuntu:20.04
FROM tomcat:8.0-jre8-alpine
RUN apt update -y
RUN apt install default-jdk -y && \
    apt install tomcat9 -y && \
    apt install maven -y && \
    apt install git -y
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
WORKDIR /boxfuse-sample-java-war-hello
RUN mvn package
RUN cp target/hello-1.0.war /var/lib/tomcat9/webapps/
EXPOSE 8080
