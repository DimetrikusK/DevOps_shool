# DevOps_shool
ssh jenkins
build_step_1:
scp -rp root@51.250.37.34:/app/jenkins/workspace/build/* /app/build/
cd /app/build/
mvn package


build_step_2:
cd /app/build/target
rm Dockerfile
echo FROM tomcat:9 >> Dockerfile
echo WORKDIR /app/build >> Dockerfile
echo ADD hello-1.0 /usr/local/tomcat/webapps/hello-1.0 >> Dockerfile
echo EXPOSE 8080:8080 >> Dockerfile
echo CMD ["catalina.sh", "run"] >> Dockerfile


build_step_3:
cd /app/build/target
docker build -t hello:1.2 .
docker tag hello:1.2 51.250.40.239:8123/hello:1.2
docker push 51.250.40.239:8123/hello:1.2


deploy_step:
docker pull 51.250.40.239:8123/hello:1.2
docker run -d --rm -p 8888:8080 51.250.40.239:8123/hello:1.2