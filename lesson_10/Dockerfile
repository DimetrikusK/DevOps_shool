FROM tomcat:9
WORKDIR /app/build
ADD hello-1.0 /usr/local/tomcat/webapps/hello-1.0
EXPOSE 8080:8080
CMD ["catalina.sh", "run"]