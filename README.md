# Spring Data Fundamentals

## Acknowledgements

This is a [LEAN**STACKS**](http://www.leanstacks.com) solution.

For more detailed information and instruction about constructing Spring Boot RESTful web services, see the book [Lean Application Engineering Featuring Backbone.Marionette and the Spring Framework](https://leanpub.com/leanstacks-marionette-spring).

LEAN**STACKS** offers several technology instruction video series, publications, and starter projects.  For more information go to [LeanStacks.com](http://www.leanstacks.com/).

## Repository

This repository is a companion for the LEAN**STACKS** YouTube channel playlist entitled [Spring Data Fundamentals](https://www.youtube.com/playlist?list=PLGDwUiT1wr693flGbjtm0WoB_722X6lNc).

### Repository Organization

Each episode of the Spring Data Fundamentals video series has a corresponding branch in this repository.  For example, all of the source code illustrated in the episode entitled [Abstracting Common Transactional Attributes into a Mapped Superclass with Spring Data JPA](https://youtu.be/_s6THdyyfN8?list=PLGDwUiT1wr693flGbjtm0WoB_722X6lNc) may be found on the repository branch named [transactional-entity](https://github.com/mwarman/spring-data-fundamentals/tree/transactional-entity).

### Branches

#### transactional-entity

The branch named `transactional-entity` contains the source code illustrated in the episode [Abstracting Common Transactional Attributes into a Mapped Superclass with Spring Data JPA](https://youtu.be/_s6THdyyfN8?list=PLGDwUiT1wr693flGbjtm0WoB_722X6lNc).

#### reference-entity

The branch named `reference-entity` contains the source code illustrated in the episode [Abstracting Common Reference Data Attributes into a Mapped Superclass with Spring Data JPA](https://youtu.be/xfgwrJmF8nY?list=PLGDwUiT1wr693flGbjtm0WoB_722X6lNc).

#### joda

The branch named `joda` contains the source code illustrated in the episode [Using JODA Framework Classes as JPA Entity Model Attributes with Spring Data JPA](https://youtu.be/OcKtf_-K5cc?list=PLGDwUiT1wr693flGbjtm0WoB_722X6lNc).

#### jpa-query-definition

The branch named `jpa-query-definition` contains the source code illustrated in the episode [Exploring Spring Data JPA Query Definition Strategies](https://youtu.be/S5vZP_03ENY?list=PLGDwUiT1wr693flGbjtm0WoB_722X6lNc).

#### jpa-mysql

The branch named `jpa-mysql` contains the source code illustrated in the episode [Using a MySQL Database with Spring Data JPA](https://youtu.be/wjpeKiTiuRE?list=PLGDwUiT1wr693flGbjtm0WoB_722X6lNc).


## Languages

This project is authored in Java.

## Installation

### Fork the Repository

Fork the [Spring Data Fundamentals](https://github.com/mwarman/spring-data-fundamentals) repository on GitHub.  Clone the project to your host machine.

### Dependencies

The project requires the following dependencies be installed on the host machine:

* Java Development Kit 8 or later
* Apache Maven 3 or later

## Running

The project uses [Maven](http://maven.apache.org/) for build, package, and test workflow automation.  The following Maven goals are the most commonly used.

### spring-boot:run

The `spring-boot:run` Maven goal performs the following workflow steps:

* compiles Java classes to the /target directory
* copies all resources to the /target directory
* starts an embedded Apache Tomcat server

To execute the `spring-boot:run` Maven goal, type the following command at a terminal prompt in the project base directory.

```
mvn spring-boot:run
```

Type `ctrl-C` to halt the web server.

This goal is used for local machine development and functional testing.  Use the `package` goal for server deployment.

### test

The `test` Maven goal performs the following workflow steps:

* compiles Java classes to the /target directory
* copies all resources to the /target directory
* executes the unit test suites
* produces unit test reports

The `test` Maven goal is designed to allow engineers the means to run the unit test suites against the main source code.  This goal may also be used on continuous integration servers such as Jenkins, etc.

To execute the `test` Maven goal, type the following command at a terminal prompt in the project base directory.

```
mvn clean test
```

### package

The `package` Maven goal performs the following workflow steps:

* compiles Java classes to the /target directory
* copies all resources to the /target directory
* executes the unit test suites
* produces unit test reports
* prepares an executable JAR file in the /target directory

The `package` Maven goal is designed to prepare the application for distribution to server environments.  The application and all dependencies are packaged into a single, executable JAR file.

To execute the `package` goal, type the following command at a terminal prompt in the project base directory.

```
mvn clean package
```

The application distribution artifact is placed in the /target directory and is named using the `artifactId` and `version` from the pom.xml file.  To run the JAR file use the following command:

```
java -jar example-1.0.0.jar
```

By default, the batch and hsqldb profiles are active.  To run the application with a specific set of active profiles, supply the `--spring.profiles.active` command line argument.  For example, to start the project using MySQL instad of HSQLDB and enable the batch process:

```
java -jar example-1.0.0.jar --spring.profiles.active=mysql,batch
```
