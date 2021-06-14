FROM openjdk:17


RUN \
    mkdir /opt/logstash && \
    cd /opt/logstash && \
    curl -O https://artifacts.elastic.co/downloads/logstash/logstash-7.13.1-x86_64.rpm && \
    rpm -i logstash-7.13.1-x86_64.rpm && \
    rm -f logstash-7.13.1-x86_64.rpm
    chown logstash:logstash -R /var/log/logstash/ && \
    chown logstash:logstash -R /var/lib/logstash/ && \
    chown logstash:logstash -R /usr/share/logstash/ && \
    chown logstash:logstash -R /etc/logstash/

# sample-1 configs
COPY ./sample-1/pipelines/* /etc/logstash/conf.d/
COPY ./sample-1/config/* /etc/logstash
COPY ./sample-1/sample_log/* /tmp/

# Example command to start sample config and send to stdout
#CMD LOGSTASH -f /etc/logstash/conf.d/sample-1.conf --path.settings /etc/logstash

ENV PATH /usr/share/logstash/bin:$PATH
    

