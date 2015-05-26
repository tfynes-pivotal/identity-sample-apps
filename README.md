# Cloud Foundry UAA Sample Applications

This repo holds separate sample applications for each one of the four OAuth 2.0 grant types.

    1. Authorization Code grant - authcode
    2. Password grant - password
    3. Implicit grant - implicit
    4. Client credentials - client_credentials

## Quick Start

Start your UAA - This can remain running while trying out different samples

    $ git clone git@github.com:cloudfoundry/uaa.git
    $ cd uaa
    $ ./gradlew run

Verify that the uaa has started by going to http://localhost:8080/uaa

Start the password grant sample application

### Using Gradle:

    $ ./gradlew :<module>:run (where module can be password, implicit, authcode, client_credentials)
    >> 2015-04-24 15:39:15.862  INFO 88632 --- [main] o.s.c.support.DefaultLifecycleProcessor  : Starting beans in phase 0
    >> 2015-04-24 15:39:15.947  INFO 88632 --- [main] s.b.c.e.t.TomcatEmbeddedServletContainer : Tomcat started on port(s): 8888 (http)
    >> 2015-04-24 15:39:15.948  INFO 88632 --- [main] o.c.i.samples.password.Application       : Started Application in 4.937 seconds (JVM running for 5.408)

### Assemble artifacts:

    $ ./gradlew assemble
    >> ./password/build/libs/password-1.0.0-SNAPSHOT.jar
    >> ./client_credentials/build/libs/client_credentials-1.0.0-SNAPSHOT.jar
    >> ./authcode/build/libs/authcode-1.0.0-SNAPSHOT.jar
    >> ./implicit/build/libs/implicit-1.0.0-SNAPSHOT.jar

### Running from command line:

    java -Dserver.port=8888 -DID_SERVICE_URL="http://localhost:8080/uaa" -DCLIENT_ID=oauth_showcase_authorization_code -DCLIENT_SECRET=secret -jar authcode/build/libs/authcode-1.0.0-SNAPSHOT.jar
    

You can test a grant flow by going to http://localhost:8888

For user grant types, login with the pre-created UAA user/password of "marissa/koala"

# Oauth Grant Sample Application

This project is a set of four sample applications for how you can set up your own application that uses a specific grant type. 
The application is written in Java uses the Spring Boot framework.

