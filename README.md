# MAVEN-OSS-PARENT-FOR-GITHUB

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.toolisticon.maven/maven-oss-parent-for-github/badge.svg)](https://maven-badges.herokuapp.com/maven-central/io.toolisticon.maven/maven-oss-parent-for-github)
![default](https://github.com/toolisticon/maven-oss-parent-for-github/workflows/default/badge.svg?branch=develop)

Maven OSS parent that supports releases build with github actions.

Enhances parent provided by https://github.com/toolisticon/maven-oss-parent.

Inspired by https://github.com/toolisticon/foss-github-actions-java

## Prerequisites

- Add maven wrapper to your project : check https://github.com/takari/maven-wrapper
- create developer branch and configure it as default
- copy .github folder from this project to your project (developer branch)
- use this projects pom.xml as parent to your project

```xml
<dependency>
    <groupId>io.toolisticon.maven</groupId>
    <artifactId>maven-oss-parent-for-github</artifactId>
    <version>0.0.1</version>
</dependency>
```

- Add secrets in your github projects settings:
```
CODECOV_TOKEN : go to http://coveralls.io and get token for your repository
GPG_OWNER_TRUST
GPG_PASSPHRASE
GPG_SECRET_KEYS
SONATYPE_PASSWORD
SONATYPE_USERNAME
```

## Workflow
The maven gitflow plugin is used to prepare and do releases. 

Development will happen on develop branch. 

Releases will be prepared and executed on a release branch an later merged and pushed to master which triggers the release build via github actions.
