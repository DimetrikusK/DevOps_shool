FROM ubuntu:20.04
RUN apt -y update && apt -y upgrade
RUN apt install -y && \
    apt install tomcat9 -y && \
    apt install maven -y && \
    apt install git -y
WORKDIR /
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
WORKDIR /boxfuse-sample-java-war-hello
RUN mvn package
RUN cp target/hello-1.0.war /var/lib/tomcat9/webapps/
CMD ["catalina.sh", "run"]
EXPOSE 80
