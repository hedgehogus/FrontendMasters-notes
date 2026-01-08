## External user management
- user login and registration
- Storing user data
- Password reset
- multi-factor authentication
- email verification
- login throttling
- logs
- token management (generating, refreshing, revoking)

## Cloud solutions - IDaaS
identity as a service     
pay for number of active users   
include free plans   
popular solutions:
- **Auth0**
- **okta**

## On-Premise solutions
Free and Open sourse
- KeyCloak
- Identity Server
- WSo2 identity server

## Authentication transaction flow at Auth0

1. An app initiates an authentication request to Auth0
2. Auth0 routes the request to an Identity Provider trough a configured connection
3. the user authenticates successfully
4. The ID token and/or Access Token is passed through the rules pipeline, then sent to the app
