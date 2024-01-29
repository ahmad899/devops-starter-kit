FROM jenkins/jenkins:alpine-jdk21 as jeknins
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false
ENV CASC_JENKINS_CONFIG /usr/share/jenkins/ref/casc.yml
USER root
RUN set -eux \
    apk update && apk add docker-cli=24.0.7-r0
USER jenkins
COPY ./plugins.txt /usr/share/jenkins/ref/plugins.txt
COPY ./casc.yml /usr/share/jenkins/ref/casc.yml
RUN jenkins-plugin-cli -f /usr/share/jenkins/ref/plugins.txt
###############################################################
FROM jenkins/ssh-agent:alpine-jdk17 as jeknins-agent
USER root
RUN set -eux \
    apk update && apk add docker-cli=24.0.7-r0
USER jenkins