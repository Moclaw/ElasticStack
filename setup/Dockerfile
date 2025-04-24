ARG ELASTIC_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/elasticsearch/elasticsearch:${ELASTIC_VERSION:-9.0.0}

COPY entrypoint.sh /entrypoint.sh
COPY lib.sh /lib.sh
COPY roles /roles

# Set the entrypoint directly without chmod
ENTRYPOINT ["/bin/bash", "/entrypoint.sh"]