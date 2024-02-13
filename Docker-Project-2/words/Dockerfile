# Base image with Java and Maven
FROM maven:3.8.4-openjdk-11 as builder
WORKDIR /app
COPY . .
RUN mvn clean verify

# Runtime stage
FROM openjdk:11-jre-slim
COPY --from=builder /app/target/words.jar /app/words.jar
WORKDIR /app
CMD ["java", "-Xmx8m", "-Xms8m", "-jar", "words.jar"]
EXPOSE 8080
