## First stage - compilation

FROM maven:3.9.6-eclipse-temurin-21-alpine AS builder

WORKDIR /worker

COPY . .

RUN mvn dependency:resolve

RUN mvn package

# ADD worker-jar-with-dependencies.jar /src/target/

## Second stage - run

FROM eclipse-temurin:21-jre-alpine

# COPY --from=builder /src/target/ /src/target/

COPY --from=builder /worker/target/worker-jar-with-dependencies.jar .

# WORKDIR /src/target/

RUN pwd

CMD ["java", "-jar", "worker-jar-with-dependencies.jar"]
