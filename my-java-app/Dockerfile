# Use Maven and JDK image
FROM maven:3.8.1-openjdk-11 AS build

# Set work directory
WORKDIR /app

# Copy the project files to the container
COPY . .

# Run Maven package command
RUN mvn clean package

# Set up a new stage to execute the built JAR file
FROM openjdk:11-jre
WORKDIR /app
COPY --from=build /app/target/my-java-app-1.0-SNAPSHOT.jar my-java-app.jar

CMD ["java", "-jar", "my-java-app.jar"]
