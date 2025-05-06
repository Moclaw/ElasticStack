FROM debian:bullseye-slim

# Install curl and tar
RUN apt-get update && apt-get install -y curl tar sudo

# Download and extract the Elastic Agent
WORKDIR /opt
RUN curl -L -O https://artifacts.elastic.co/downloads/beats/elastic-agent/elastic-agent-9.0.0-linux-x86_64.tar.gz \
    && tar xzvf elastic-agent-9.0.0-linux-x86_64.tar.gz \
    && rm elastic-agent-9.0.0-linux-x86_64.tar.gz

WORKDIR /opt/elastic-agent-9.0.0-linux-x86_64

# Run the install command during container startup (optional)
CMD ["./elastic-agent", "install", \
     "--fleet-server-es=http://elasticsearch:9200", \
     "--fleet-server-service-token=AAEAAWVsYXN0aWMvZmxlZXQtc2VydmVyL3Rva2VuLTE3NDY1MTg4MTg4ODM6eG14NHlvTWJRd09RTm9fLUhOdmdmQQ", \
     "--fleet-server-policy=fleet-server-policy", \
     "--fleet-server-port=8220", \
     "--install-servers"]
