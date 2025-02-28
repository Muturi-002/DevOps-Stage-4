FROM maven:3.8.4-openjdk-11-slim AS build

WORKDIR /users-api

# Copy the pom.xml and download dependencies
COPY pom.xml .

# Copy the source code and build the application
COPY src ./src
RUN mvn package -DskipTests

# Reduce build time by using a smaller base image
FROM openjdk:8-jre-slim

WORKDIR /users-api

# Copy the built application JAR file from the first stage
COPY --from=build /users-api/target/*.jar ./users-api.jar

EXPOSE 8083

# Define the command to run the application
CMD ["java", "-jar", "users-api.jar"]
