
FROM --platform=linux/amd64 maven:3.8.6-eclipse-temurin-11-alpine as builder 

WORKDIR /app

COPY src /app/src

COPY pom.xml /app

RUN mvn verify

FROM  --platform=linux/amd64 openjdk:8-jre-slim

COPY --from=builder /app/target/hello-java.jar /app/hello-java.jar

ENTRYPOINT [ "java", "-jar", "/app/hello-java.jar" ]

