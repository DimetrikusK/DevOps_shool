FROM ubuntu:18.04
RUN apt update -y
RUN apt install default-jdk -y && \
    apt install tomcat9 -y && \
    apt install maven -y && \
    apt install git -y
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
RUN cd /boxfuse-sample-java-war-hello/ && \
    mvn package
RUN cp /boxfuse-sample-java-war-hello/target/hello-1.0.war /var/lib/tomcat9/webapps/
RUN javac Main.java
CMD ["java", "Main"]
EXPOSE 8080
