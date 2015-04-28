# Usage #

## Implementing the Interfaces ##

### SpringSecurityAuthenticatorAdapter ###

This class is responsible for bridging the gap and adapting the ESAPI and Spring methods to work together in harmony. There are a handful of _helper_ methods exposed by the ESAPI Authenticator Interface that must be implemented in your application. In addition, there is one important method that you must implement. This is the method that assembles the AuthenticatedUser.

**Authentication getAuthentication(T,UserDetails,List[GrantedAuthority](GrantedAuthority.md))**

This method is responsible for assembling an instance of AuthenticatedUser which is an adapter class between the ESAPI User interface and the Spring-Security UserDetails interface. It must return an implementation of the Spring-Security Authentication interface - many are provided by the Spring-Security library itself - or you can build your own.

|**Authentication**|**Description**|
|:-----------------|:--------------|
|AnonymousAuthenticationToken|Represents an unauthenticated user|
|JaasAuthenticationToken|Represents a user who has been authenticated using a JAAS Service|
|PreAuthenticatedAuthenticationToken|Represents a user who has been pre-authenticated (SiteMinder, etc)|
|RememberMeAuthenticationToken|Represents a user who has been authenticated by the RememberMeService|
|RunAsUserToken|Represents a user who is authenticated on behalf of another|
|TestingAuthenticationToken|Should only be used for unit testing|
|UsernamePasswordAuthenticationToken|Represents a user who has been authenticated by the UsernamePasswordAuthenticationFilter|

**void afterPropertiesSet() throws Exception**

This method is important if you are using an authenticator that is intended to be used as a singleton (which by default all Spring beans are unless otherwise scoped) Due to the way the ESAPI Locator works and how Spring works, it is necessary to add a getInstance method to the implementation if it is a singleton.

```
public class MyAuthenticator extends SpringSecurityAuthenticatorAdapter {
   private static Authenticator INSTANCE;

   public static Authenticator getInstance() {
      return INSTANCE;
   }

   // ...

   public void afterPropertiesSet() throws Exception {
      INSTANCE = this;
   }

   // ...
}
```

**String generateStrongPassword()**

See http://owasp-esapi-java.googlecode.com/svn/trunk_doc/latest/org/owasp/esapi/Authenticator.html#generateStrongPassword()

**String generateStrongPassword(User,String)**
See [java.lang.String)](http://owasp-esapi-java.googlecode.com/svn/trunk_doc/latest/org/owasp/esapi/Authenticator.html#generateStrongPassword(org.owasp.esapi.User,)

**User getUser(long)**

In most production systems, this method will not be needed or used and should throw a RuntimeException or a Compile-time Error. In some implementation, this method is used to retrieve a User object identified by the primary key.

**User getUser(String)**

This method can be used to retrieve an implementation of the User interface identified by the passed in username. This is a useful method for loading a user profile for display or for managing users by creating applicable User implementations (ie: UserProfileView, ManagedUserProfile)

**Set getUserNames()**

This method should be called when "creating" a user to ensure that the username is not already present in the realm.

**String hashPassword(String,String) throws EncryptionException**

If you are managing your own password storage, this method should be called prior to saving and verifying the supplied password.

**void verifyAccountNameStrength(String) throws AuthenticationException**

This method is generally used to ensure that an account name meets an established account name policy. Duplicate username checks, format checks, length checks and so on can be verified here. This method should be called as part of the user creation process.

**void verifyPasswordStrength(String,String,User) throws AuthenticationException**

This method should be called during initial account creation and when a password change is initiated.

### AuthenticationStrategy ###

The AuthenticationStrategy is the mechanism that will actually interact with your user repository, be it LDAP, Database, or FileSystem - this is where you will actually perform the task of verifying a users credentials to authenticate them.

**T authenticate(Authentication) throws AuthenticationException**

**User createUser(String, String password)**

**void changePassword(String, String newPassword)**

**void deleteUser(String)**

**boolean userExists(String)**

### UserDetailsService ###

This interface is provided by Spring-Security and is required for retrieving the UserProfile object from the user datasource.

### AuthoritiesPopulator ###

**List[GrantedAuthority](GrantedAuthority.md) getAuthoritiesForUser(Authentication)**

### UserProfile ###

This class represents the Entity that holds all the information returned by the ESAPI User Interface.

## Configuration ##

### Configuring ESAPI ###

You will need to update your ESAPI.properties to use the Authenticator implementation (class that extends SpringSecurityAuthenticatorAdaptor)

```
# ESAPI.properties
ESAPI.Authenticator=com.mycompany.app.MyAuthenticator
```

### Configuring Spring ###

You will need to add the following into your applicationContext.xml file

```
    <bean id="esapiSpringAuthenticatorPropertyPlaceholder" class="org.springframework.beans.factory.config.PropertyPlaceholderConfigurer">
        <property name="location" value="classpath:/SpringAuthenticator.properties"/>
    </bean>

    <import resource="classpath*:/org/owasp/esapi/contrib/spring/authenticator/esapi-spring-security-context.xml"/>

    <bean id="authenticationProvider" class="com.mycompany.app.MyAuthenticator" scope="singleton">
        <property name="authenticationStrategy" ref="authenticationStrategy" />
        <property name="authoritiesPopulator" ref="authoritiesPopulator" />
        <property name="userDetailsService" ref="userDetailsService" />
    </bean>

    <bean id="authenticationStrategy" class="com.mycompany.app.MyAuthenticationStrategy"/>
    <bean id="authoritiesPopulator" class="com.mycompany.app.MyAuthoritiesPopulator"/>
    <bean id="userDetailsService" class="com.mycompany.app.MyUserDetailsService"/>
```

Next you will need to create a SpringAuthenticator.properties

```
Authenticator.LoginUrl=/user/login
Authenticator.AuthenticationUrl=/user/authenticate
Authenticator.SuccessUrl=/home/dashboard
Authenticator.FailureUrl=/user/login/?error=true
Authenticator.UsernameParameterName=username
Authenticator.PasswordParameterName=password
Authenticator.AuthenticateOnPostOnly=true
```