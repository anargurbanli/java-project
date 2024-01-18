# Java-Project
Simple Java Project which runs on Tomcat. Inside Tomcat container runs Filebeat service which provides tomcat web access logs to Kafka container. Kafka receives logs with topic and send it to Logstash. Logstash send logs to ELK Stack. All containers running on Docker-Compose Environment. Pull project and push it to your CI/CD environment.

##Check Containers status
$ docker ps
![image](https://github.com/anargurbanli/java-project/assets/47213126/4d644170-e01c-45b2-8c77-b784d078aa43)

##Check Java Web Tomcat 
http://localhost:8080
![image](https://github.com/anargurbanli/java-project/assets/47213126/f837d3b4-d567-4e42-9954-12e03d393acc)

##Check Kafka Consumer 
1. Run command with docker container id
$ docker exec -it <docker container id> kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic hello-world-topic
2. Refresh web page(http://localhost:8080) and wait for logs 
![image](https://github.com/anargurbanli/java-project/assets/47213126/b10ec518-51c2-4e70-8540-d5a5e88d5af6)

##Check Logstash (index name: hello-world-logs)
$ curl -X GET "localhost:9200/_cat/indices?v"
![image](https://github.com/anargurbanli/java-project/assets/47213126/84b472ae-53b5-4c0d-a900-2a75cc751bbe)

##Check ELK
1. Open web url on browser http://localhost:5601
2. Create new index
3. Discover logs
![image](https://github.com/anargurbanli/java-project/assets/47213126/a8e98981-1c1b-4349-a76b-3ea8fc13b823)

