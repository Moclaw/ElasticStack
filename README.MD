# Elastic Stack Docker Environment

This project provides a complete Elastic Stack (ELK) environment using Docker Compose. It includes Elasticsearch, Kibana, Logstash, Filebeat, Metricbeat, Heartbeat, Curator, and Fleet, all pre-configured for easy local development and testing.

## Prerequisites

- Windows OS (tested)
- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed and running
- [Docker Compose](https://docs.docker.com/compose/) (included with Docker Desktop)

## Getting Started

1. **Clone the repository**

   ```sh
   git clone https://github.com/Moclaw/ElasticStack.git
   cd ElasticStack
   ```

2. **Setup profile**

   ```sh
      docker-compose --profile=setup up setup -d
   ```

3. **Start the Elastic Stack**

   ```sh
      docker-compose up -d
   ```

   This command will start all services in the background.

4. **Access the Services**
   - **Elasticsearch:** <http://localhost:9200>
   - **Kibana:** <http://localhost:5601>
   - **Logstash:** Configured via pipeline in `logstash/pipeline/`
   - **Filebeat, Metricbeat, Heartbeat, Curator, Fleet:** Managed via their respective folders and compose files in `extensions/`

## Run fleet and apm server

   ```sh
   sudo docker-compose -f docker-compose.yml -f extensions/fleet/fleet-compose.yml -f extensions/fleet/agent-apmserver-compose.yml up -d
   ```


## Configuration

- Each service has its own configuration files under its respective folder (e.g., `elasticsearch/config/elasticsearch.yml`).
- You can customize these files as needed for your use case.
- For advanced setup, check the `extensions/` directory for additional tools and their configs.

## Stopping the Stack

To stop all services:

```sh
   docker-compose down
```

## Troubleshooting

- Ensure Docker Desktop is running before starting the stack.
- If ports are already in use, stop conflicting services or change the ports in the `docker-compose.yml` file.
- Check logs with:

  ```sh
  docker-compose logs <service-name>
  ```

## More Information

- [Elasticsearch Documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)
- [Kibana Documentation](https://www.elastic.co/guide/en/kibana/current/index.html)
- [Logstash Documentation](https://www.elastic.co/guide/en/logstash/current/index.html)
- [Beats Documentation](https://www.elastic.co/guide/en/beats/libbeat/current/index.html)

---

Feel free to explore the `extensions/` directory for additional tools and their usage instructions.
