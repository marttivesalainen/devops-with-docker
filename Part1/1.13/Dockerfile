FROM openjdk:latest

EXPOSE 8080
COPY . /usr/app
WORKDIR /usr/app

RUN ./mvnw package

CMD java -jar ./target/docker-example-1.1.3.jar