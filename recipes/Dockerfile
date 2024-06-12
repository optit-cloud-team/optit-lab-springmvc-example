# Use the official Maven image to build the application
FROM maven:3.8.5-openjdk-17 AS build
WORKDIR /app

# Copy the pom.xml and download dependencies
COPY pom.xml .
RUN mvn dependency:go-offline

# Copy the source code and build the application
COPY src ./src
RUN mvn clean package -DskipTests

# Use the official OpenJDK image to run the application
FROM openjdk:17-jdk-slim
WORKDIR /app

# Copy the built .war file from the build stage
COPY --from=build /app/target/recipes-0.0.1-SNAPSHOT.war /app/app.war

# Expose the port the application will run on
EXPOSE 7071

# Command to run the application
CMD ["java", "-jar", "app.war"]
