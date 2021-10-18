FROM jenkins/jenkins:latest
USER root

RUN apt-get update && apt-get install docker.io -y

RUN curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose 
RUN chmod +x /usr/local/bin/docker-compose 
RUN ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

USER jenkins
RUN jenkins-plugin-cli --plugins "blueocean:1.24.7 docker-workflow:1.26"
