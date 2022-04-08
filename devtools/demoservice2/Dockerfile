FROM maven:3.6-jdk-8 as builder
COPY . /code/
WORKDIR /code
RUN --mount=type=cache,target=/root/.m2 mvn package

FROM openjdk:8-jre
COPY --from=builder /code/target/*.jar /usr/app/
WORKDIR /usr/app
CMD [ "java", "-jar", "demoservice-0.0.1-SNAPSHOT.jar" ]