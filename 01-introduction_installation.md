# CHAPTER 01 - APACHE MAVEN - INTRODUCTION AND INSTALLATION

Maven Goals:
* Easing the build process.
* Providing a uniform build system.
* Providing quality project information.
* Providing guidelines for best practice development.
* Allowing transparent migration to new features.

Maven Solves this by:
* Providing a set of build standars: Convention over configuration by using well-defined project structures.
* An artifact repository model: Maven downloads dependencies automatically.
* An engine describing projects.
* A standard lifecycle (build, test, deploy)

Maven internally is composed of 4 components:
* Maven Wagon: Transport abstraction for repository handling (http, ftp, ssh, file, webdav)
* Maven Doxia: Content generation (static/dynamic content) for publishing web/wikis/etc
* Maven Modello: Generates artifacts (Java POJO, XML, etc)
* Maven SCM: Source Code Management operations for Git, CVS, Subversion, etc.

# CHAPTER 02 - INSTALLING M2ECLIPSE

* Eclipse m2Eclipse has an embedded Maven. Installing an external Maven helps with continuos integration.
* Eclipse > Preference > Maven > Installations > Add External Maven (directory)

# CHAPTER 03 - CREATING AND IMPORTING PROJECTS

## Project Configuration's Standard Convention

Main Components:
* `pom.xml` Project's pom file
* `src/main/java` Application's Java source files
* `src/main/resources` Application's resources (images, sounds, templates, etc)
* `target` Output of the build
* `src/test/java` Unit test files
* `src/test/resources` Unit testing-specific resources
* `src/site` Site artifacts
* `src/main/webapp` Sources files for web applications

Other Components:
* `src/filters` Test-specific filter for resources
* `src/it` Integration tests files (primarily for plugins )
* `src/assembly` Assembly descriptors
* `src/main/filters` Resource's filter files
* `src/main/config` Configuration files of the application
* `src/main/scripts` Application-specific scripts
* `LICENSE.txt` Projects license
* `NOTICE.txt` Notice and attributions that the project depends on
* `README.txt` This denotes the project's readme information

This conventions can be overwritten.

## POM (Project Object Model)
* pom.xml is an XML with all the major details/settings of the proje532ct.
* Analogous to `make` and Ant's `build.xml`

### Coordinates
A project/component is identified by:
* groupId: by convention com.mydomain , but also `junit` ok.
* artifactId: often package name
* version
* packaging: if unspecified default is *.jar (ejb, war, etc)

Maven transforms the  4 id's into 1 sequence of folders `com\mydomain\myId\1.0\myId.jar

```xml
                                <!-- represents the basis packaging structure -->
<groupId>com.myDomain</groupId> <!-- translates to $M2_REPO/com/myDomain -->
<groupId>junit</groupId>        <!-- translates to $M2_REPO/junit -->

<artifactId>myId</artifactId>   <!-- -->

```



