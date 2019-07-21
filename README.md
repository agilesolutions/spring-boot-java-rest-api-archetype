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

## Jenkind CDP Continuous Deployment pipelines

* [Setting up continuous deployment pipelines](./docu/jenkins-cdp.md)


## Jenkins CI/CD integration
* [read devops tools 2.4](https://github.com/vfarcic/vfarcic.github.io/blob/master/devops24/jenkins-cdp-demo.md)
* [follow the devops tools md pages](https://github.com/vfarcic/vfarcic.github.io/tree/master/devops24)
* [watch the presentation](http://vfarcic.github.io/devops24/workshop-4h.html#/7/4)
* kubeaps search stable/jenkins
* download https://github.com/helm/charts/tree/master/stable/jenkins
* helm install stable/jenkins -name jenkins --namespace jenkins
* kubectl -n jenkins rollout status deploy jenkins
* helm inspect stable/jenkins
* helm ls
* helm status jenkins
* kubectl -n kube-system get cm
* kubectl -n kube-system describe cm jenkins.v1
" kubectl -n jenkins get all
* kubectl -n jenkins describe deploymetn jenkins
* helm delete jenkins --purge
* helm inspect values stable/jenkins
* customize the jenkins helm setups with the values from the jenkins folder
* Install the jenkins pipelins shared libraries from Jenkins-shared-libraries directory


Procedure for deploying to Maven Central https://central.sonatype.org/pages/apache-maven.html

Create or update archetypes and set version to SNAPSHOT (ex: 1.0.0-SNAPSHOT)

Deploy SNAPSHOT version to https://oss.sonatype.org/content/repositories/snapshots/

`spring-boot-java-rest-api-archetype> ./mvn clean deploy -P release`

Deploy release version to Maven Central

```
spring-boot-java-rest-api-archetype> ./mvn release:clean release:prepare -P release
spring-boot-java-rest-api-archetype> ./mvn release:perform -P release
```
