## Use java 11 to build.

## Create github client
https://github.com/settings/developers
#### Redirect URI
http://localhost:8080/login/oauth2/code/github

#### If curity running on self signed cert, add it to java trust store
1. Download curity cert. 
```
cd $JAVA_HOME/lib/security
```

2. Check if theres a certificate already installed

```
keytool -list -trustcacerts -keystore ~/apps/jdk-11/lib/security/cacerts -storepass changeit|grep localhost
```

3. if so remove it

```
keytool -delete -trustcacerts -keystore ~/apps/jdk-11/lib/security/cacerts -storepass changeit -alias localhost
```

4. Install the new cert
```
keytool -import -trustcacerts -keystore ~/apps/jdk-11/lib/security/cacerts -storepass changeit -alias localhost -file curitycert
```
