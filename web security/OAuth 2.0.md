The OAuth 2.0 authorization framework enables a third-party application to obtain limited access to an HTTP service 

## Problem to solve - limited information sharing between accounts
e.g. sharing contacts list

## Access Token
- lifetime
- scope

## Roles in OAuth
- **Client** - an application making protected resourse request on behalf of the resourse owner
- **Resource owner** - capable of granting access to a protected resourse
- **Authoriation server** - issuing access tokens to the client
- **Resource server** - hosting the protected resources

## Client types in OAuth
- **public client** - secret cannot be stored securely (pure spa without backend)
- **confidential client** - able to store secret securely

## authorization grant 
A way to get an Access Token   
1) Credential representing ownrs authorization used by the client to obtain an access token
2) Grant Type defines th Oauth flow
Two types
- implicit (legacy) (response_type=token)
- Authorization Code (response_type=code)
- refresh Token (access_type=offline)
- client credentials
- other grants

## Security measures
- use encrypted channel (HTTPS only)
- review the scopes on the consent screen
- authorization code lifetime (must expire shortly after it is issued to mitigate the risks of leaks)
- state parameter (random string prevents from csrf attacks) (state=abcd1234)
- strict redirect_url matching (do not use pattern matching like **.somesite.com)
- refresh token rotation (a new refresh token is issued with every access token refresh response)

## Proof key for code Exchange (PKCE, "pixy")
An extension to the authorization code flow opening the gates for Public clients   
1. 'state' secures the first step from CSRF attack (this step was missing before pkce)    
     
```
&code_challenge=CODE_CHALLENGE
&code_challenge_method=S256
```
1. Generate very long, random secret value - **Code Verifier**
2. Store **Code Verifier** it in the local storage
3. Generate SHA256 hash from **Code Verifier - Code Challange**
4. Pass **Code Challenge** and **hashing method** with the request
5. Authorization server **calculates the hash** from the provided **Code Verifier** and compares it with the **code Challenge**
6. Match? Then **Access Token** is issued

- PKCE provides a "dynamic secret" or one-time password for Public Clients
- It mitigates the risk of stolen authorization Code
- Public Client must authenticate itself (Confidential Client uses client_id + client_secret)
- Verification is executed by the authorization server
   
