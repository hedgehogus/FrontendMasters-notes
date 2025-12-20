# Cross site scripting
## Types
- Reflected XSS (by query params)
- Stored XSS

- Server-side XSS (traditional)
- Dom-based XSS

## stored example 
```
<img src="xyz" style="display: none" onerror="alert(`I have your cookies: ${document.cookie}`);">
```

fixes by sanityzation and Content Security Policy

# Cross-site request forgery
## how to prevent

1. Anti-CSRF tokens    
   ``` Set-Cookie: Csrf-Token=123random_unique_token```    
   request:   
   ```HTTP Header: X-Csrf-Token: 123random_unique_token```   
3. SameSite Cookies (same site strict cookies attribute)   
   same-site: lax - allows top level navigation

# Hacking JWT Tokens
- can expose information about user
- algorythm type can be set to "none" in versions <=1.3.0
- changing "RS256"(asymmetric algorithm) to "HS256"(symmetric)
- brute forcing the "secret" (secret should be strong, long and complicated)
- JWT getting stolen (have a short expiry date) - 20 minutes after issuing
