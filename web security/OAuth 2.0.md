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
