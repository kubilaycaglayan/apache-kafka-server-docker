# README

## Resources

- https://kafka.apache.org/quickstart
- https://www.kafkatool.com/download.html

## Instructions

### Start the Docker image

`docker compose up`

### Start the monitoring tool

- Create new Kafka cluster in Offset Explorer
  - Bootstrap servers: localhost:9092

### Creating producer and consumer

- You can use terminal:

`docker exec -it ${image_id} /bin/sh`

- Or the docker exec terminal to run the next commands:

- In Docker image navigate

`cd ../opt/kafka/bin/`

- Create a topic as in https://kafka.apache.org/quickstart

`./kafka-topics.sh --create --topic quickstart-events --bootstrap-server localhost:9092`

- Verify the creation of the topic on console and in Offset Explorer

`./kafka-topics.sh --list --bootstrap-server localhost:9092`

- Write a message to the topic

`./kafka-console-producer.sh --topic quickstart-events --bootstrap-server localhost:9092`

- Read the message from the topic (create consumer)

`./kafka-console-consumer.sh --topic quickstart-events --from-beginning --bootstrap-server localhost:9092`
