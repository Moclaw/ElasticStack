ARG ELASTIC_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/elasticsearch/elasticsearch:${ELASTIC_VERSION:-9.0.0}

COPY entrypoint.sh /entrypoint.sh
# Fix permission issue by ensuring entrypoint.sh is executable
RUN chmod +x /entrypoint.sh && \
    # Make sure it has the right permissions
    chmod 755 /entrypoint.sh

COPY lib.sh /lib.sh
# Also ensure lib.sh has correct permissions
RUN chmod 755 /lib.sh

COPY roles /roles