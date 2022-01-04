# 04jan2022
FROM ubuntu:jammy-20211122
RUN apt-get update && apt-get install openjdk-8-jdk -y
RUN cd /opt && apt-get install wget -y
RUN wget  https://dlcdn.apache.org/tomcat/tomcat-8/v8.5.73/bin/apache-tomcat-8.5.73.tar.gz
RUN tar -xvf  apache-tomcat-8.5.73.tar.gz &&  mv apache-tomcat-8.5.73 tomcat8 && chmod 777 -R tomcat8 && cd tomcat8
CMD ["catalina.sh", "run"]
