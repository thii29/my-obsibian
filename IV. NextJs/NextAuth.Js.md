### OAuth 
**Refer:**
https://youtu.be/q3FiuTZlroE?si=KxLRJrThOi8i15HR
https://viblo.asia/p/tim-hieu-doi-chut-ve-oauth2-eW65GvMLlDO

An **authorization framework** that enables **a third-party application** to obtain **limited** access to an **HTTP service**

###  4 roles of OAuth
Resource owner: Users have ability give access permission.
Resource server: place to stored resource
Client: Third-party need to access Resource server
Authorization: Have task is identify check informations user request & response also create access token code

### Work flow
1. The application requests authorization to access service resources from the user
2. If the user authorized the request, the application receives an authorization grant
3. The application requests an access token from the authorization server (API) by presenting authentication of its own identity, and the authorization grant
4. If the application identity is authenticated and the authorization grant is valid, the authorization server (API) issues an access token to the application. Authorization is complete.
5. The application requests the resource from the resource server (API) and presents the access token for authentication
6. If the access token is valid, the resource server (API) serves the resource to the application

![[oauth-flow.png]]

### Credentials
Reference at: https://next-auth.js.org/configuration/providers/credentials




