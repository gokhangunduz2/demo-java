FROM gradle:8-jdk17 AS builder

WORKDIR /app

COPY . .

RUN gradle build

# debug
RUN ls -ltra build/libs

FROM eclipse-temurin:17

WORKDIR /app

COPY --from=builder /app/build/libs/*SNAPSHOT.jar app.jar

RUN ls -ltra

CMD ["java", "-jar", "app.jar"]
