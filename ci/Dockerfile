FROM gradle:8-jdk17 AS builder

WORKDIR /app

COPY .. .

RUN gradle build

RUN ls -ltra

FROM eclipse-temurin:17

WORKDIR /app

RUN cd build

RUN cd libs

RUN ls -ltra

COPY --from=builder /build/libs/demo-0.0.1-SNAPSHOT.jar app.jar

CMD ["java", "-jdk", "app.jdk"]
