# Jakarta EE 10 Web Project Template

This project template is designed for Jakarta EE 10 web applications. It includes Lombok for reducing boilerplate code and a Maven plugin for easy deployment to GlassFish.

## Created by

Koleff Martín Samuel

## Project Specifications

- **Jakarta EE Version**: 10
- **Java Version**: 17
- **Build Tool**: Maven
- **Application Server**: GlassFish
- **Additional Libraries**: Lombok

## Configuration Files

- `beans.xml`: Version 4.0
- `web.xml`: Version 6.0
- `persistence.xml` and `orm.xml`: Version 3.0

## Setup and Deployment

### Prerequisites

1. Java 17 JDK
2. Maven
3. GlassFish Server

### GlassFish Configuration

Before deploying, you need to set up a password file for GlassFish:

1. Navigate to your GlassFish home directory
2. Create a `password.properties` file with the following command:
    ```sh
    echo 'AS_ADMIN_PASSWORD=your_password' > password.properties
    ```
    (Replace `your_password` with your actual GlassFish admin password.)

### Deployment

To deploy the application to GlassFish, run the following Maven command:
```sh
mvn clean package glassfish:deploy
```
This command will compile the project, package it into a WAR file, and deploy it to your GlassFish server.

## Project Structure

- `src/main/java`: Java source files
- `src/main/resources`: Configuration files (including `persistence.xml` and `orm.xml`)
- `src/main/webapp`: Web resources
  - `WEB-INF/beans.xml`: CDI configuration
  - `WEB-INF/web.xml`: Web application configuration
- `src/test`: Test files

## Persistence Configuration

This project includes a sample `persistence.xml` file configured for Hibernate. You may need to adjust the datasource and other properties to match your specific database setup.

## Additional Notes

- The project uses Lombok to reduce boilerplate code. Ensure your IDE has Lombok support or the appropriate plugin installed.
- The GlassFish Maven plugin is configured in the `pom.xml` file. You may need to adjust the `glassfishDirectory` property to match your GlassFish installation path.

## Local Installation

To install the archetype locally, first clone the repository and navigate to the root directory of the project:
```sh
git clone https://github.com/Samuel-Koleff/jakarta10-archetype.git
cd jakarta10-archetype
mvn clean install
```

Then, to create a new project using this archetype, run:
```sh
mvn archetype:generate -DarchetypeCatalog=local -DarchetypeGroupId=jakarta10-archetypes -DarchetypeArtifactId=jakarta10-webapp-archetype
```

---
