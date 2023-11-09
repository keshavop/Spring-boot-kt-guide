#### 1. Create a spring boot app
#### 2. Make sure that while running app should not throw any execption or bugs
#### 3. In ```application.properties``` file mention all the database configuration commands
```
spring.datasource.url=jdbc:postgresql://localhost:5432/postgres
spring.datasource.username=postgres
spring.datasource.password=postgres

spring.datasource.driver-class-name=org.postgresql.Driver
spring.jpa.hibernate.ddl-auto=update
```

#### 4. Create ```dockerfile``` in directory
```
#FROM amazoncorretto:17-alpine-jdk
#
## Create a directory
#WORKDIR /app
#
## Copy all the files from the current directory to the image
#COPY . .
#
## build the project avoiding tests
#RUN ./gradlew clean build
#
## Expose port 8080
#EXPOSE 8080
#
## Run the jar file
#CMD ["java", "-jar", "./build/libs/crud-0.0.1-SNAPSHOT.jar"]


# Use the official OpenJDK image as a parent image
FROM openjdk:11-jre-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the JAR file (the Spring Boot application) to the container
COPY . .

# Expose the port your Spring Boot application listens on
EXPOSE 8080

# Define the command to run your Spring Boot application when the container starts
CMD ["java", "-jar", "./build/libs/crud-0.0.1-SNAPSHOT.jar"]


```

#### 5. Create ```docker-compose.yml``` file in directory
```
version: '3'
services:
  postgres:
    image: postgres:latest
    container_name: crud-kotlin-app
    environment:
      POSTGRES_DB: jdbc:postgresql://localhost:5432/postgres
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres
    ports:
      - 5432:5432

  spring-boot-app:
    build:
      context: .
      dockerfile: Dockerfile
    container_name: your-spring-boot-container-name
    ports:
      - 8080:8080
    depends_on:
      - postgres

```