FROM jenkins/jenkins:2.190.1

MAINTAINER Serhii Matsak

USER root

RUN curl -o /tmp/filebeat-7.6.1-amd64.deb https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.6.1-amd64.deb && \
    dpkg -i /tmp/filebeat-7.6.1-amd64.deb &&  apt-get install

COPY filebeat/filebeat.yml /etc/filebeat/filebeat.yml

COPY ["entrypoint.sh", "/"]

RUN chmod +x /entrypoint.sh

ENTRYPOINT ["/bin/bash","-c","./entrypoint.sh"]
