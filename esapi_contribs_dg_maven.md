## The Parent POM ##

All ESAPI Components are required to use the ESAPI-Contrib Parent POM. This will define some basic configuration for your project, namely reporting requirements and the Maven Site Template

```
    <parent>
        <groupId>org.owasp.esapi.contrib</groupId>
        <artifactId>esapi-contrib-parent</artifactId>
        <version>1.0.0</version>
    </parent>
```

## Build Parameters and Requirements ##

Since ESAPI 2.0GA is built on a Java 5 baseline, it is recommended that your component use the same - however, if you have a particular reason you want to use a new JDK be sure to document the JDK requirements

## Deployment / Releases ##

If you wish for your component to be available from Maven Central, you must submit it for approval. Once your component is approved, you will be required to check it into the subversion repository and an ESAPI Project Manager will perform a release for you. Snapshot releases can be deployed nightly once our new CI Server is up and running.