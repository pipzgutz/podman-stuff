# KAFKA KRAFT MODE

## Initialize the KRaft Metadata

Before starting Kafka, initialize the metadata log directory:

```bash
podman run --rm \\
  -v ./data:/var/lib/kafka/data \\
  confluentinc/cp-kafka:latest \\
  kafka-storage format \\
  --config /etc/kafka/kafka.properties \\
  --cluster-id $(kafka-storage random-uuid)
```

## Start Kafka in KRaft Mode

```bash
podman-compose up -d
```

## Verify Kafka is Running in KRaft Mode

```bash
podman logs <container_name>
```
