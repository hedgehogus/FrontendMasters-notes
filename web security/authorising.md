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
