FROM openjdk:11

RUN apt-get update -y && \
    apt-get upgrade -y

#install maven
RUN wget https://mirrors.estointernet.in/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz && \
    tar -xvf apache-maven-3.6.3-bin.tar.gz && \
    mv apache-maven-3.6.3 /opt/

#install docker
RUN for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do apt-get remove $pkg; done
RUN install -m 0755 -d /etc/apt/keyrings
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg
RUN chmod a+r /etc/apt/keyrings/docker.gpg
RUN echo \
      "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
      "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
      sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
RUN apt-get update
RUN apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

#RUN apt-get install -y apt-transport-https ca-certificates curl software-properties-common
#RUN curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
#RUN echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb\_release -cs) stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null
#RUN apt-get update
#RUN apt-cache policy docker-ce
#RUN install docker-ce

#clear cache
RUN apt-get clean

