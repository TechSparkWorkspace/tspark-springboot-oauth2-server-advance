# TechSpark OAuth 2.0 Authorization Server

This project is a Spring Boot application that provides an OAuth 2.0 Authorization Server. It uses
the [Spring Security](https://spring.io/projects/spring-security) framework to secure the application and provide OAuth
2.0 support.

## Setup the Project

- Run `https://github.com/TechSparkWorkspace/tspark-springboot-oauth2-server-advance.git`  clone the repository
- Run `cd tspark-springboot-oauth2-server-advance` to navigate to the project directory.
- Run `./gradlew build` to build the project.
- Run `./gradlew bootRun` to start the application.
  - The application will be accessible at http://localhost:8080.

## Generate an access token

Once the Spring Boot application is up and running you can use the below command to generate an OAuth token from the
authorization server

```shell
curl -u my-client:secret \
  -d "grant_type=client_credentials" \
  http://localhost:8080/oauth2/token
```

_Note:_ Adjust the port number if your Spring Boot application runs on a port other than 8080.




