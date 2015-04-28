# Installation #

## Maven ##

If your project is using Maven you can simple add this component as a dependency to your project.

```
<project>
   ...
   <dependencies>
      ...
      <dependency>
         <groupId>org.owasp.esapi.contrib</groupId>
         <artifactId>esapi-spring-authenticator</artifactId>
         <version>1.0.0</version>
      </dependency>
      ...
   </dependencies>
   ...
</project>
```

## Manual Installation ##

Download the latest version of the component from the [Downloads](http://code.google.com/p/owasp-esapi-java/downloads/list?q=label:Contribs) page and copy into your `<web-app>/WEB-INF/lib` directory.

## Build from Source ##

Check the code out from subversion

```
https://owasp-esapi-java.googlecode.com/svn/contrib/spring/authenticator/esapi-spring-authenticator/trunk
```

Change to the directory where you checked the project out and build with

```
mvn clean install
```

The binary jar will be in the `<project_root>/target` directory when the build completes.