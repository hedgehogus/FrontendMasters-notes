## Types
- Reflected XSS (by query params)
- Stored XSS

- Server-side XSS (traditional)
- Dom-based XSS

## stored example 
```
<img src="xyz" style="display: none" onerror="alert(`I have your cookies: ${document.cookie}`);">

fixes by sanityzation and Content Security Policy
