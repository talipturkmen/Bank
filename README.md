# Bank (UserFront / OnlineBanking)

> **Archived.** This is a 2018 course/learning project and is no longer maintained. Dependencies are outdated and contain known vulnerabilities; do not deploy as-is.

A server-rendered online banking web application. Users register and log in, view their primary and savings accounts, make transfers, and submit and confirm appointment requests. The application includes a user-management area for enabling and disabling users.

## Tech stack

- Java 1.8
- Spring Boot 1.4.1 (Spring Security, Spring Data JPA / Hibernate, Thymeleaf)
- MySQL (`mysql-connector-java`)
- Maven (wrapper included)
- Bootstrap 3 and jQuery (bundled as static files)

## Repository structure

- `UserFront/`: the Spring Boot application
  - `src/main/java/com/userfront/`: controllers, services, DAOs, domain entities, security configuration
  - `src/main/resources/templates/`: Thymeleaf templates
  - `src/main/resources/static/`: CSS, JavaScript, fonts, images
  - `src/main/resources/application.properties`: database and JPA settings
- `AdminPortal/`: an empty entry (a nested repository reference with no `.gitmodules`). It has no content in this repository.

## Running it

This is best-effort documentation; the project was not re-run during the cleanup.

1. Install JDK 8 and MySQL, and start MySQL on `localhost:3306`.
2. Create a database named `OnlineBanking`. Hibernate is set to `ddl-auto=update`, so tables are created on first start.
3. Check the datasource credentials in `UserFront/src/main/resources/application.properties` (the defaults are `root` / `sesame`).
4. From `UserFront/`, run `./mvnw spring-boot:run`.
5. Open http://localhost:8080.

## Known issues

- Database credentials are hard-coded in `application.properties`.
- The BCrypt salt is a hard-coded constant (`"salt"`) in `SecurityConfig.java`.
- This code is not suitable for real use. See the archive note above.
