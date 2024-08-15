# mosquitto-pro-docker

+ [Pro Edition of Eclipse Mosquitto](https://cedalo.com/mqtt-broker-pro-mosquitto/) is used. You can request a [free 30-day trial period](https://cedalo.com/mqtt-broker-pro-mosquitto/trial-signup/)

+ Login to the Cedalo container registry

```
docker login registry.cedalo.com
```

+ Start the containers 
```
docker-compose up -d
```

+ Configuration and dashboard setup in Grafana with Data source http://influxdb:8086 and token, org and bucket set in docker-compose.yml

+ Stop and delete the containers
```
docker-compose stop
docker container rm $(docker ps -aq)
```


