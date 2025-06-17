FROM jenkins/jenkins:lts-jdk17
USER root

# Install tools
RUN apt-get update && \
    apt-get install -y lsb-release curl gnupg2 software-properties-common

# Docker CLI install
RUN curl -fsSLo /usr/share/keyrings/docker-archive-keyring.asc \
  https://download.docker.com/linux/debian/gpg && \
  echo "deb [arch=$(dpkg --print-architecture) \
  signed-by=/usr/share/keyrings/docker-archive-keyring.asc] \
  https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list && \
  apt-get update && apt-get install -y docker-ce-cli

# Maven install
RUN apt-get update && \
    apt-get install -y maven

USER jenkins
