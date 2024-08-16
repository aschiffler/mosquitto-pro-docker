# mosquitto-pro-docker with enabled InfluxDB metrics exporter plugin
[Documentation is here](https://docs.cedalo.com/mosquitto/broker/Mosquitto%20Manual/mosquitto-metrics-exporter/#influxdb-metrics-exporter)

Extend the mosquitto.conf by

```
global_plugin /usr/lib/cedalo_metrics_influxdb.so
plugin_opt_update_interval 60
plugin_opt_host http://inflxudb:8086
plugin_opt_organisation devteam
plugin_opt_bucket mosquitto
plugin_opt_token changeme
```

## Setup and Test

+ [Pro Edition of Eclipse Mosquitto](https://cedalo.com/mqtt-broker-pro-mosquitto/) is used. You can request a [free 30-day trial period](https://cedalo.com/mqtt-broker-pro-mosquitto/trial-signup/)

+ Login to the Cedalo container registry

```
docker login registry.cedalo.com
```

+ Start the containers 
```
docker compose up -d
```

+ Configuration and dashboard setup in Grafana with Data source http://influxdb:8086 and token, org and bucket set in docker-compose.yml

+ Stop and delete the containers
```
docker compose stop
docker container rm $(docker ps -aq)
```


