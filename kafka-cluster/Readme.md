### This will install Kafka and redis clusters locally

- if you are using Mac M chip processor then better uncomment `kafka-ui` section and comment or remove `kafdrop`

- but if you want to use Kafdrop then need to uncomment `platform: linux/amd64` line as this will force to run on linux/amd64 mode

- if you don't need `redis` you can comment out redis block also

- if you run this somewhere other than localhost replace `localhost` of this line with your IP `KAFKA_CFG_ADVERTISED_LISTENERS=PLAINTEXT://localhost:9092,PLAINTEXT_INTERNAL://kafka:9093`

# Run the cluster

## start

`docker-compose up -d`

here `-d` use to run in detached mode. if you need to see logs remove `-d`

## stop

`docker-compose stop`

## remove cluster

`docker-compose down`
