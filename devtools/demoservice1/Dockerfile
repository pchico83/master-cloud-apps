FROM maven:3.6-jdk-8 as builder
COPY . /code/
WORKDIR /code
RUN mvn package

FROM openjdk:8-jre
COPY --from=builder /code/target/*.jar /usr/app/
RUN ls -al /usr/app/ && sleep 10
WORKDIR /usr/app
CMD [ "java", "-jar", "demoservice-0.0.1-SNAPSHOT.jar" ]