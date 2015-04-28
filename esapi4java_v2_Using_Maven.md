ESAPI is available from both Maven Central, or the ESAPI Sonatype Snapshot Repository.

**Important: If you use Maven, this will not include the ESAPI Configuration Files - this only gets the required jars to run ESAPI in your application.**

You can also download a zip of all the example configurations and documentation [here](http://code.google.com/p/owasp-esapi-java/downloads/detail?name=esapi-2.0_rc11-config.zip&can=2&q=)

To use ESAPI with Maven - you can add the following to your pom.xml

**If you want to use Releases from Maven Central**
```
   <dependencies>
      <dependency>
         <groupId>org.owasp.esapi</groupId>
         <artifactId>esapi</artifactId>
         <version>2.1.0</version>
      </dependency>
   </dependencies>
```

**If you want to use Snapshot Releases** (Do not use Snapshots in Production Applications! No guarantees are made to the reliability of these builds, these are nightly or on-demand snapshot builds of the trunk - They should be used for development and evaluation purposes only). Previous releases are 2.0GA and 2.0.1.
```
    <repositories>
        <repository>
            <!-- For ESAPI Snapshots -->
            <id>snapshots.oss.sonatype.com</id>
            <name>googlecode-snapshots at sonatype.com</name>
            <url>https://oss.sonatype.org/content/repositories/snapshots/</url>
            <releases>
                <enabled>false</enabled>
            </releases>
            <snapshots>
                <enabled>true</enabled>
            </snapshots>
        </repository>
    </repositories>

   <dependencies>
      <dependency>
         <groupId>org.owasp.esapi</groupId>
         <artifactId>esapi</artifactId>
         <version>2.0.1-SNAPSHOT</version>
      </dependency>
   </dependencies>
```