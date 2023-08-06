FROM tomcat:9
ADD target/hello-1.0.war /usr/local/tomcat/webapps/hello-1.0
EXPOSE 8080:8080
CMD ["catalina.sh", "run"]