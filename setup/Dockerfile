ARG ELASTIC_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/elasticsearch/elasticsearch:${ELASTIC_VERSION:-9.0.0}

COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

COPY lib.sh /lib.sh
COPY roles /roles