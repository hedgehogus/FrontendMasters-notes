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
   same-site: lax
