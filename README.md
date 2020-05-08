# spring-security-OAuth2-Facebook
oauth2 authorization code flow using Facebook as Authorization and Resource server


1. Create an App using Facebook for developers
2. Obtain the Client ID and Client Secret provided by facebook
3. Download pom.xml to download all required dependenices (only annotation required is @EnableOAuth2Sso)
4. Make a request to http://localhost:8080
5. The application will redirect the user to the 
   userAuthorizationUri: https://www.facebook.com/dialog/oauth
6. Once facebook verifies the client from the client Id and client secret, it redirects the user to facebook login form
7. Once user enters user id and password, facebook will authenticate the user and provides the authorization code to the client
8. The Client now will provide the authorization code to the url
    accessTokenUri: https://graph.facebook.com/oauth/access_token to obtain the access token
9. Now the client uses the access token to the facebook resource server to request the user data from facebook
10. Here facebook is both the Authorization and Resource server. In some cases, both the servers can be separate entities

Similarly, the client app can be created in amny platforms like Github, Google, Okta etc and the respective client id and client secret along
with respective urls should be used in the property file

<img width="1000" alt="API Architecture" src="https://github.com/dineschandgr/spring-security-OAuth2-Facebook/blob/master/Authorization_Code_Flow.bmp">




You can also get the access token from postman app. use postman console or the chrome developer tools Network tab to check the request and response header/body

