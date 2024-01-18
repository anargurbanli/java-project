# Java-Project
Simple Java Project which runs on Tomcat. Inside Tomcat container runs Filebeat service which provides tomcat web access logs to Kafka container. Kafka receives logs with topic and send it to Logstash. Logstash send logs to ELK Stack. All containers running on Docker-Compose Environment

## Usage
- __$ git clone https://github.com/anargurbanli/java-project.git__ \
Clone and add project to your local GitHub Repository and Run Pipline
