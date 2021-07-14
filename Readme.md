We must ensure that the service names and KAFKA_BROKER_ID are unique across the services.

Moreover, each service must expose a unique port to the host machine. So, although zookeeper-1 and zookeeper-2 are listening on port 2181, 
they're exposing it to the host via ports 22181 and 32181, respectively. The same logic applies for the kafka-1 and kafka-2 services, 
where they'll be listening on ports 29092 and 39092, respectively.

1. test zookeeper

nc -z localhost 22181
nc -z localhost 32181

2. test brokers

docker-compose logs kafka-1 | grep -i started
docker-compose logs kafka-2 | grep -i started

3. Para usar los comandos de creacion de topics en osx -> brew install kafka (pero no arrancar los servicios).
