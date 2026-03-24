FROM gradle:8-jdk17 AS builder

WORKDIR /app

COPY .. .

RUN gradle build

FROM openjdk:17

WORKDIR /app

COPY --from=builder /build/libs/demo-0.0.1-SNAPSHOT.jar app.jar

CMD ["java", "-jdk", "app.jdk"]


