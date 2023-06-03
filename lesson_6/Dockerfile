#FROM ubuntu:20.04
FROM tomcat:8.0-jre8-alpine
RUN yum update -y
RUN yum install default-jdk -y && \
    yum install tomcat9 -y && \
    yum install maven -y && \
    yum install git -y
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
WORKDIR /boxfuse-sample-java-war-hello
RUN mvn package
RUN cp target/hello-1.0.war /var/lib/tomcat9/webapps/
EXPOSE 8080
