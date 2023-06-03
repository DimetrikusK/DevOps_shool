FROM ubuntu:20.04
RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install -y default-jdk wget maven git
    #yum install tomcat9 -y && \
    #yum install maven -y && \
    #yum install git -y
WORKDIR /
RUN git clone https://github.com/boxfuse/boxfuse-sample-java-war-hello.git
WORKDIR /boxfuse-sample-java-war-hello
RUN mvn package
RUN cp target/hello-1.0.war /var/lib/tomcat9/webapps/
CMD ["catalina.sh", "run"]
