FROM ubuntu:18.04
RUN apt update -y
RUN apt install default-jdk -y && \
    apt install tomcat9 -y && \
    apt install maven -y && \
    apt install git -y
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
RUN cd /boxfuse-sample-java-war-hello/ && \
    mvn package
RUN cp target/hello-1.0.war /var/lib/tomcat9/webapps/
EXPOSE 8080
