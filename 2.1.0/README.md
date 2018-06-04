This is a fork of [jkleczkowski/teamcity-agent-dotnet-core](https://github.com/jkleczkowski/teamcity-agent-dotnet-core). It also uses [jetbrains/teamcity-agent/](https://hub.docker.com/r/jetbrains/teamcity-agent/) as a base, which includes:

- ubuntu:xenial
- git
- curl, unzip (linux)
- mercurial
- Oracle **JRE 8 Update 161, 64 bit**
- Open JDK 8
- docker-engine (Linux):
  - v.1.9.1 (TeamCity agent 9.1.7)
  - v.1.10.3 (TeamCity agent 10.0 - 10.0.4)
  - v.1.13.0 (TeamCity agent 10.0.5 - 2017.1.2)
  - v.17.06.0-ce (TeamCity agent 2017.1.3+)
  - v.17.12.0-ce (TeamCity agent 2017.2.2+)

This docker image adds the following technologies:

- Dotnetcore-2.1-sdk
- nodejs-10.x
- Ansible
- Gulpjs
- Bowerjs
- Mono



# How to Use This Image

Pull `docker pull chuckconway/teamcity-agent-dotnetcore-2.1-sdk`

use the following command to start a container with TeamCity agent running inside Linux container:

```
docker run -it -e SERVER_URL="<url to TeamCity server>"  \ 
    -v <path to agent config folder>:/data/teamcity_agent/conf  \      
    chuckconway/teamcity-agent-dotnetcore-2.1-sdk
```
