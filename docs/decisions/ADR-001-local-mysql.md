# ADR-001: Local MySQL Database

## Status

Accepted

## Context

Credix requires a relational database for persistent application data.

The project uses MySQL with Spring Data JPA and Flyway for schema migration management.

## Decision

MySQL will run locally using Docker.

Spring Boot and the React frontend will run directly on the host machine.

Flyway will manage all database schema changes.

Database credentials will be provided through environment variables and will not be committed to Git.

## Consequences

### Positive

- Reproducible local database environment
- No MySQL installation required on the host
- Database lifecycle is isolated from the application
- Database schema changes are version controlled
- Credentials can remain outside Git

### Negative

- Docker is required for local database development
- Developers need to understand basic Docker volume/container management

## Scope

Docker is used only for the local MySQL database.

Docker will not be used to run:

- Spring Boot
- React
- CI/CD
- Production deployment