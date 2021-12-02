# Maven Parent POM
Top level POM file for Maven projects so that they all behave the same way and utilize the same libraries

## Project Information
### settings.xml
Add the following repository to your settings.xml file so you can access the dependencies published there.

    <profiles>
      <profile>
        <id>github</id>
        <repositories>
          <repository>
            <id>github</id>
            <url>https://maven.pkg.github.com/mgabelmann/*</url>
            <snapshots>
              <enabled>true</enabled>
            </snapshots>
          </repository>
        </repositories>
      </profile>
    </profiles>
    
    <activeProfiles>
      <activeProfile>github</activeProfile>
    </activeProfiles>
    
### pom.xml
Add the following to your projects pom.xml file to inherit from the parent pom.
    
    <parent>
      <groupId>ca.mikegabelmann.maven</groupId>
      <artifactId>parent</artifactId>
      <version>1.0-SNAPSHOT</version>
    </parent>

## Local Usage
Due to the way GitHub works you will need a Personal Access Token (PAT) with package read access to download
this dependency from GitHub. Alternatively you can download this project and build it locally and install it
into your local Maven repository.

    mvn package install

See pom.xml above to add the parent project to your project and then you will be able to build it without
GitHub access.
