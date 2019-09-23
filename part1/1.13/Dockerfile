# FROM openjdk:14
FROM openjdk:latest

WORKDIR /

RUN yum install -y git

RUN git clone https://github.com/docker-hy/spring-example-project.git
WORKDIR /spring-example-project/ 
RUN ./mvnw package


CMD java -jar ./target/docker-example-1.1.3.jar

EXPOSE 8080

