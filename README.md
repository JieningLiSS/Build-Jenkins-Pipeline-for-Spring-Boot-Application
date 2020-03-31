# Build-Jenkins-Pipeline-with-Nexus-for-Spring Boot Application 

Create a Jenkins Pipeline for Spring Boot Application with Nexus Repository Manager

## Prerequisite

-[Install Jenkins](https://jenkins.io/doc/book/installing/)

-[Install Nexus](https://help.sonatype.com/repomanager3/download)

## Step 1: Configure Java_home,GIT,Maven,Gradle for Jenkins

1. Goto Jenkins default running port localhost:8080.

2. Under Manage Jenkins > Global Tool Configuration, put your path directory for Java_home,GIT,Maven,Gradle.

3. Under Manage Jenkins > Manage Plugin, install git, pipeline, nexus plugins.

## Step 2: Configure Nexus

1. Goto Nexus default running port localhost:8081.

2. Login with default user name: admin, password: admin123.

## Step 3: Configure Maven Deploy to Nexus

1.  Configure Nexus for maven repository by adding following codes in your pom.xml.

```html
<distributionManagement>
  <snapshotRepository>
    <id>nexus-snapshots</id>
    <url>http://localhost:8081/repository/maven-snapshots/</url>
  </snapshotRepository>
</distributionManagement>
```

2.  Configure Maven Settings with the credentials for Nexus by adding following codes in your setting.xml.

```html
<server>
  <id>nexus-snapshots</id>
  <username>admin</username>
  <password>Queens297</password>
</server>
```

## Step 4: Build Jenkins Pipeline project

1. Goto Jenkins Home > New Item > Create Project with Pipeline.

2. Goto Pipeline > Pipeline Script from SCM > Git > Repostory URL > Save

3. Click Build Now.
