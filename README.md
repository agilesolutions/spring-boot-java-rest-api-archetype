# spring-boot-java-rest-api-archetype

## How to use?

This archetype is not published to Maven central. 
You can generate project using this archetype using `mvn archetype:generate` and select the archetype number.

### Install archetype locally

```bash
git clone https://github.com/agilesolutions/spring-boot-java-rest-api-archetype.git
cd spring-boot-java-rest-api-archetype
./mvn clean install
```

### Generate application from archetype

```
mvn archetype:generate \
    -B -DarchetypeGroupId=ch.agilesolutions.springboot \
    -DarchetypeArtifactId=spring-boot-java-rest-api-archetype \
    -DarchetypeVersion=0.0.1 \
    -DgroupId=com.mycompany \
    -DartifactId=myapp \
    -Dversion=1.0-SNAPSHOT \
    -Dpackage=com.mycompany.myapp
```

Generates basic SpringBoot REST API application with the following features:

* Database support (H2/Postgres)
* Configured Dockerfile, Jenkinsfile
* Flyway DB migrations
* Monitoring with Prometheus, Grafana
* ELK based logging

## Developer Notes

Procedure for deploying to Maven Central https://central.sonatype.org/pages/apache-maven.html

Create or update archetypes and set version to SNAPSHOT (ex: 1.0.0-SNAPSHOT)

Deploy SNAPSHOT version to https://oss.sonatype.org/content/repositories/snapshots/

`spring-boot-java-rest-api-archetype> ./mvn clean deploy -P release`

Deploy release version to Maven Central

```
spring-boot-java-rest-api-archetype> ./mvn release:clean release:prepare -P release
spring-boot-java-rest-api-archetype> ./mvn release:perform -P release
```