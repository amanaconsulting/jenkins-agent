# jenkins-agent
Jenkins Agent Docker image

This is a docker image for Jenkins, it is based on the official [jenkins/agent](https://hub.docker.com/r/jenkins/agent) image, which includes JDK and the Jenkins agent executable (agent.jar). This executable is an instance of the [Jenkins Remoting library](https://github.com/jenkinsci/remoting).
The base image was extended with a Docker client and German language and time zone settings.
JDK version depends on the image and the platform, see the _Configurations_ section below.


## Configurations

The image has several supported configurations, which can be accessed via the following tags:

* Linux Images:
  * `jdk17` : Preview JDK17 version with the newest remoting (based on `debian:bullseye-${builddate}`) 
  * `jdk11` : Latest version with the newest remoting and Java 11 (based on `debian:bullseye-${builddate}`)
  * `jdk8` : Latest version with the newest remoting and Java 8 (based on `debian:bullseye-${builddate}`)
