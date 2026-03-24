FROM gradle:8-jdk17 AS builder

WORKDIR /app

COPY .. .

RUN gradle build

RUN ls -ltra

FROM eclipse-temurin:17

WORKDIR /app

RUN ls -ltra

