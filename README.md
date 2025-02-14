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

## Token Introspection

Call the Token Introspection endpoint to verify whether a token is active (valid) and gather metadata about it.

```shell
curl -u my-client:secret \
     -X POST \
     -d "token=ACCESS_TOKEN_GOES_HERE" \
     http://localhost:8080/oauth2/introspect
```

## Requesting Token with a Permitted Scope

Generating a token for permitted scope example: `read` will look like this:

```shell
curl -u my-client:secret \
     -d "grant_type=client_credentials" \
     -d "scope=read" \
     http://localhost:8080/oauth2/token
```

## Requesting Token for a Non-Permitted Scope

Try requesting a scope the client isn't allowed (for instance, admin)

```shell
curl -u my-client:secret \
     -d "grant_type=client_credentials" \
     -d "scope=admin" \
     http://localhost:8080/oauth2/token
```
