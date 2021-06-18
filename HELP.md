## Use java 11 to build.

## Create github client
https://github.com/settings/developers
#### Redirect URI
http://localhost:8080/login/oauth2/code/github

#### If curity running on self signed cert, add it to java trust store
1. Download curity cert. 
```
cd $JAVA_HOME/lib/security
keytool -import -trustcacerts -keystore cacerts -storepass changeit -alias localhost -import -file curity_cert 
```