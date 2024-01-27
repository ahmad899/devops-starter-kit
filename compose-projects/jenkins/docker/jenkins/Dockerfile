FROM jenkins/jenkins:alpine-jdk21 as jeknins
USER root
RUN set -eux \
    apk update && apk add docker
USER jenkins
RUN jenkins-plugin-cli --plugins "blueocean docker-workflow"
###############################################################
FROM jenkins/ssh-agent:alpine-jdk17 as jeknins-agent
USER root
RUN set -eux \
    apk update && apk add docker
USER jenkins

