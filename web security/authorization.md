# Authentication vs Authorization
## Authentication 
proves one's identity
- login and password
- secret sink sent via email
- secret code send via sms
- iris scan
- fingerprint scan
- other something unique

## Authorization
Grants access to the system resources
**Access control** - protection of system resources against unauthorized access

## Access control models
- Mandatory Access Control(MAC)
- Discretionaly Access Control(DAC)
- History-Based Access Control(HBAC)
- Attribute-Based Access Control(ABAC)
- others
- Role-Based Access Control (RBAC)

## Vectors of authorization
- ownership (does the entity belong to th users account)
- role (does the user have the owner/reader role)
- other rules (sharing entities betwee accounts. Like reading/liking a comment)

## server side security 
- server side validation
- http security headers
- TLS encryption (HTTPS)

## http security headers
- content-security-policy
- strict-transport-Security: max-age=63072000; includeSubDomains \\ for https
- iframe and embedded: X-Frame-Options: deny/sameorigin

## not available without https
- service workers
- push notifications
- geolocations
- webcam
- bluetooth
- other PWA features

## free and open certificate authotrity (https)
letsencrypt.org

## when to use Session cookies
- single server web app
- no need for enterprise scaling
- you have an access to backend
- most of time is just anough

## JWT tokens
- distributed enterprise environment
- multiple domains/origins
- no way to implement a session mechanism
- securing 3rd party API
- passing short-lived grants (downloading a file, accessing some endpoints)
- protocols like OAuth2/OpenId
