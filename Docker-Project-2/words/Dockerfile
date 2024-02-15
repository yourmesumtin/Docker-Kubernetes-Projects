# Base image with Java and Maven
FROM ubuntu:22.04
WORKDIR /app
COPY . ./
RUN apt-get update -y && \
    apt-get install default-jre -y && \ 
    apt-get install maven -y && \
    apt-get clean && \
    mvn verify

WORKDIR /app/target

CMD ["java", "-Xmx8m", "-Xms8m", "-jar", "words.jar"]
EXPOSE 8080
