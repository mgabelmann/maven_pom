# maven_pom
Top level POM file for Maven projects so that they all behave the same way and utilize the same libraries

## settings.xml
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
    
## pom.xml
Add the following to your projects pom.xml file to inherit from the parent pom.
    
    <parent>
      <groupId>ca.mikegabelmann.maven</groupId>
      <artifactId>parent</artifactId>
      <version>1.0-SNAPSHOT</version>
    </parent>
