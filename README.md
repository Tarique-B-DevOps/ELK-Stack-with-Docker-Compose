# ELK Stack with Docker Compose

## What is ELK Stack?
The **ELK Stack** (Elasticsearch, Logstash, and Kibana) is a powerful log management and analysis system. It helps collect, process, store, and visualize logs from various sources.

### Components of ELK Stack:
1. **Elasticsearch** – Stores and indexes logs for fast searching.
2. **Logstash** – Collects, processes, and forwards logs to Elasticsearch.
3. **Kibana** – Visualizes log data and provides dashboards.

## Use Cases
- **Log Monitoring**: Track system and application logs in real-time.
- **Security Analysis**: Detect suspicious activities and anomalies.
- **Performance Monitoring**: Analyze server and application performance metrics.
- **Troubleshooting**: Identify and debug system issues quickly.

## Why Use Docker Compose?
Docker Compose makes it easy to manage multi-container applications like ELK. Instead of manually starting each container with different configurations, a `docker-compose.yml` file defines everything in one place. This ensures consistency, simplifies deployment, and allows all components to work together seamlessly.

## Starting a Simple ELK Stack Using Docker Compose

### Prerequisites
- **Docker Compose version v2.32.4 and later**

### Running the ELK Stack
Run the following command to start the ELK stack in detached mode:

```bash
docker-compose up -d
```

This starts **Elasticsearch**, **Logstash**, and **Kibana** as Docker containers.

### Accessing Services
- **Elasticsearch:** http://localhost:9200  
- **Kibana:** http://localhost:5601  

### Viewing Logs in Kibana
1. Open **Kibana** at `http://localhost:5601`
2. Go to **Stack Management → Index Patterns**
3. Create an index pattern for `apt-logs`
4. Go to **Discover** and select `apt-logs` to view log data

### Stopping the Stack
To stop and remove the ELK stack, run:

```bash
docker-compose down
```

## Note
- The example in this setup collects logs from `/var/log/apt/history.log`. If you need to change the log source, update `logstash.conf`and docker volume with the correct file paths.