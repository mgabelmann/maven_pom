# Maven Parent POM
Top level POM file for Maven projects so that they all behave the same way and utilize the same libraries

## Project Information

### settings.xml
If you have a Personal Access Token (PAT) then add the following section to your settings.xml

    <profiles>
      <profile>
        <id>github-mgabelmann</id>
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

    <servers>
      <server>
        <id>github</id>
        <username>USERNAME</username>
        <password>PAT</password>
      </server>
    </servers>

### Local Usage
Alternatively you can download this project and build it locally and install it into your local 
Maven repository.

    git clone https://github.com/mgabelmann/maven_pom.git

    mvn package install

### pom.xml
Once you have either updated your settings.xml or installed the project in your local Maven repository then you can
begin using it by adding it to your local project(s).

    <parent>
      <groupId>ca.mikegabelmann.maven</groupId>
      <artifactId>parent</artifactId>
      <version>1.0-SNAPSHOT</version>
    </parent>

