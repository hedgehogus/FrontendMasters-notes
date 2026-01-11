## Web sockets securituy
- same origin policy
- user authentification
- origin spoofing
- input validation and sanitization
- TCP tinneling
- Denial of Service
- Encryption

## same origin policy
web sockets are not subject to same-origin policy   
use Content security Policy (based on origin) for web sockets
- Http Headers
- Meta http-eguiv
```
connect-src 'self' ws://localhost:8080;
```

## user authentification

No build-in authentications (same to HTTP) use tokens and cookies    

Croos-site WebSocket hijacking (cswsh)
- sameSite cookie (none/lax/strict)
- validate Origin header

## input validation and sanitization
use schema and sanityze values using libs like https://joi.dev

## TCP tunneling
- ports open in internet (HTTP(80), FTP(21))
- ports behind the firewall - only in intranet (SSH(22), MySQL(3306))    
  There are tools that allow us to easily tunnel arbitrary tcp connections via web sockets - **firewalls bypassing!!!**      
  using these bridges are very risky

## Denial of Service
- limit the number of open connections per client
- content delivery network + DDoS mitigation

## WSS (encryption)
wss:// to ws://       
is what        
https:// is to http://
