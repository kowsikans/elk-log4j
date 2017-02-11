# How to connect log4j with Logstash, ElasticSearch and Kibana
With several log4j configurations, you can  monitor your logs with ELK.
Normally you can use the images for Kibana and Elasticsearch direct, without to build the image with a Dockerfile. 
### Get started
```docker
docker-compose up
```
### Sample log4j configuration:
``` properties
# Root logger option
log4j.rootLogger=INFO, socket

# Direct log messages to stdout
log4j.appender.stdout=org.apache.log4j.ConsoleAppender
log4j.appender.stdout.Target=System.out
log4j.appender.stdout.layout=org.apache.log4j.PatternLayout

log4j.appender.socket=org.apache.log4j.net.SocketAppender
log4j.appender.socket.port=9988
log4j.appender.socket.remoteHost=localhost
log4j.appender.socket.reconnectionDelay=10000
log4j.appender.socket.application=Test
```