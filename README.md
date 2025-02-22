# Simple ELK Stack with Docker Compose

## Running the ELK Stack
Run the following command to start the ELK stack in detached mode:

```sh
docker-compose up -d
```

This starts **Elasticsearch**, **Logstash**, and **Kibana** as Docker containers.

## Accessing Services
- **Elasticsearch:** [http://localhost:9200](http://localhost:9200)
- **Kibana:** [http://localhost:5601](http://localhost:5601)

### Viewing Logs in Kibana
1. Open **Kibana** at `http://localhost:5601`
2. Go to **Stack Management → Index Patterns**
3. Create an index pattern for `apt-logs`
4. Go to **Discover** and select `apt-logs` to view log data

## Stopping the Stack
To stop and remove the ELK stack, run:

```sh
docker-compose down
```
