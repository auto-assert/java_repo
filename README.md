# java_repo

## Getting Started
This API is saves and returns user data at the following endpoints

POST http://localhost:8080/api/users - saves a user to the repository using the following sample request 

`{"name":"John Doe","email":"john.doe@example.com"}`

GET http://localhost:8080/api/users - returns all saved users

GET http://localhost:8080/api/users/1 - returns a user by the id

## Prerequisites

### Check to see your current version
`java -version`

### Install JDK 17 if not already installed

`brew install --cask temurin@17 --arm64`

### Set JDK 17 to JAVA_HOME

Add the following to ./bashrc, ./zshrc, and ./bash_profile

`export JAVA_HOME=$(/usr/libexec/java_home -v 17)`

### Install Java certs if you have not already

1.  Navigate to https://repo.maven.apache.org/

2.  In chrome 
        -  click the secured lock in the browser
        -  Choose connection is secure
        -  Choose Certificate is valid
        -  Click the Details Tab and click Export at the bottom and save to your computer somewhere
3.  Import the Certificate into the Java Truststore

        `keytool -import -alias custom-cert -keystore $JAVA_HOME/lib/security/cacerts -file /path/to/your/downloaded/certificate.pem`
    
    Replace /path/to/your/downloaded/certificate.pem with the actual path to the certificate file.
    
    *** Note:  you may need to use sudo if you get a permissions error ***

4. The default password for the Java truststore is `changeit`.

## Run Unit Tests

`./gradlew test`

## Start server and run API locally
Hit each endpoint listed above in Postman or by using curl after running the following:

`./gradlew bootRun`
