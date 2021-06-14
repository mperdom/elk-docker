# open jdk 11 - Debian
FROM openjdk:11

# Debian 
RUN \
    apt-get update && \
    apt-get install -y vim && \
    mkdir /opt/logstash && \
    cd /opt/logstash && \
    curl -O https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-7.13.1-amd64.deb && \
    dpkg -i elasticsearch-7.13.1-amd64.deb && \
    rm -f elasticsearch-7.13.1-amd64.deb && \
    chown elasticsearch:elasticsearch -R /var/log/elasticsearch/ && \
    chown elasticsearch:elasticsearch /var/lib/elasticsearch && \
    chown elasticsearch:elasticsearch -R /usr/share/elasticsearch/ && \
    chown elasticsearch:elasticsearch -R /etc/elasticsearch/ && \
    chown elasticsearch:elasticsearch /etc/default/elasticsearch

COPY ./config/elasticsearch.yml /etc/elasticsearch/elasticsearch.yml

ENV PATH=$PATH:/usr/share/elasticsearch/bin

CMD ["elasticsearch"]