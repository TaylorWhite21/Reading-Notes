

## [What is OAuth?](https://www.csoonline.com/article/3216404/what-is-oauth-how-the-open-authorization-framework-works.html)

1. What is OAuth?
    - OAuth allows websites and services to share assets among users.
2. Give an example of what using OAuth would look like.
    - An example would be when you go to a website and they offer one or more options to login.
3. How does OAuth work? What are the steps that it takes to authenticate the user?
<!-- Copied from the reading as it explains it way better than I can -->
```
The first website connects to the second website on behalf of the user, using OAuth, providing the user’s verified identity.

The second site generates a one-time token and a one-time secret unique to the transaction and parties involved.

The first site gives this token and secret to the initiating user’s client software.

The client’s software presents the request token and secret to their authorization provider (which may or may not be the second site).

If not already authenticated to the authorization provider, the client may be asked to authenticate. After authentication, the client is asked to approve the authorization transaction to the second website.

The user approves (or their software silently approves) a particular transaction type at the first website.
The user is given an approved access token (notice it’s no longer a request token).

The user gives the approved access token to the first website.
The first website gives the access token to the second website as proof of authentication on behalf of the user.
The second website lets the first website access their site on behalf of the user.

The user sees a successfully completed transaction occurring.
OAuth is not the first authentication/authorization system to work this way on behalf of the end-user. 

In fact, many authentication systems, notably Kerberos, work similarly. What is special about OAuth is its ability to work across the web and its wide adoption. It succeeded with adoption rates where previous attempts failed (for various reasons).
``` 
4. What is OpenID?
    - OpenID is an authentication method for humans to login to machines.

## [Authorization and Authentication flows](https://auth0.com/docs/flows)

1. What is the difference between authorization and authentication?
    - Authorization is the process of verifying what a user is able to see and Authentication is the process of verifying a users identity.

2. What is Authorization Code Flow?
    - It exchanges an Authorization Code for a token.

3. What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?
    - When public clients (e.g., native and single-page applications) request Access Tokens, some additional security concerns are posed that are not mitigated by the Authorization Code Flow alone.

4. What is Implicit Flow with Form Post?
    -  It is intended for Public Clients, or applications which are unable to securely store Client Secrets.

5. What is Client Credentials Flow?
    - With machine-to-machine (M2M) applications, such as CLIs, daemons, or services running on your back-end, the system authenticates and authorizes the app rather than a user.

6. What is Device Authorization Flow?
    - With input-constrained devices that connect to the internet, rather than authenticate the user directly, the device asks the user to go to a link on their computer or smartphone and authorize the device. This avoids a poor user experience for devices that do not have an easy way to enter text. To do this, device apps use the Device Authorization Flow (ratified in OAuth 2.0), in which they pass along their Client ID to initiate the authorization process and get a token.

7. What is Resource Owner Password Flow?
    - It is not recommended, highly-trusted applications can use the Resource Owner Password Flow (defined in OAuth 2.0 RFC 6749, section 4.3), which requests that users provide credentials (username and password), typically using an interactive form.
