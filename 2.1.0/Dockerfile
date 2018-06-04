FROM jetbrains/teamcity-agent
LABEL maintainer "Chuck Conway <charles@cconway.com>"

RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 417A0893 && \
    apt-get update && \
    apt-get upgrade -y && \
    apt-get install wget -y && \ 
    apt-get install tzdata -y && \
    # Install Microsoft's Offical Ubuntu package
    wget -q https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb && \
    dpkg -i packages-microsoft-prod.deb && \
    apt-get install apt-transport-https -y && \
    apt-get update -y && \
    apt-get install dotnet-sdk-2.1 -y && \
    # Install Mono-Development
    apt-get install mono-devel mono-dbg mono-xbuild libmono-addins-* -y && \
    # Install Nodejs and install web tools which are required for "dotnet publish" command
    apt-get remove nodejs npm && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash - && \
    apt-get install nodejs -y && \
    npm install npm -g && \
    npm install bower gulp -g && \
    # Install Ansible
    echo "deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main" >> /etc/apt/sources.list && \
    apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367 && \
    apt-get update && \
    apt-get install -y ansible

VOLUME /opt/buildagent/work
VOLUME /opt/buildagent/logs
VOLUME /data/teamcity_agent/conf
VOLUME /opt/buildagent/plugins

ENV DOCKER_HOST ""
ENV DOCKER_BIN "/usr/bin/docker"
