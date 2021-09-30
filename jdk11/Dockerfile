FROM jenkins/agent:latest-jdk11
LABEL maintainer = "dennis.jansen@amana.de"
ARG DEBIAN_FRONTEND="noninteractive"
ARG DEBCONF_NOWARNINGS="yes"
ARG DEBCONF_TERSE="yes"
ARG user=jenkins
ARG group=jenkins
ARG uid=1000
ARG gid=1000

USER root
RUN apt-get -yqq update && apt-get -yqq install --no-install-recommends curl apt-utils zip && rm -rf /var/lib/apt/lists/*

# Install Docker Client
# so war es bisher: RUN curl -sSL https://get.docker.com/ | sh
RUN curl --silent -fsSL https://get.docker.com/ -o get-docker.sh
RUN sh get-docker.sh
RUN usermod -aG docker jenkins

USER ${user}

# Change Jenkins time zone
ENV JAVA_OPTS -Dorg.apache.commons.jelly.tags.fmt.timeZone=Europe/Berlin -Duser.timezone=Europe/Berlin -Duser.country=DE -Duser.language=de

# Set the locale
ENV LANG de_DE.UTF-8
