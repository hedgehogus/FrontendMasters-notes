## Who is the OWASP fundation?

THe Open Web Application Security Progect is a nonprofit foundation that works to improve the security of software

## OWASP 10
is a standart awareness document for developers and web application security

## 1. SQL injections
always validate and sanitize all user inputs

## 2. broken Authentication
- Automated attaks, 
- default, weak or well-known passwords
- plain text storage or weakly hashed     
**fixes:**
- Multi factor authentication
- Password checking during registration
- imposing password complexity rules (min length, special characters etc)
- Limiting failed login attempts

## 3. Sensitive data exposure
- never trasmit data over the network in a clear text (https)
- enforce HTTPS with HTTP Strict Transport Security (HSTS)
- never use old or weak cryptographic algorithms
- never store sensitive data in plain text (use strong hashing like bcrypt)

## 4. XML External Entities (XXE)
attackers can exploit vulnerable XML processors if they can upload XML or include hostile content in an XML document
``<!ENTITY xxe SYSTEM "file:///ets/passwd"> ] >``    
Not that important for web developers, but good to know when dealing with enterprise systems

## 5. Broken access control
- entity (account) ownership check
- proper role
- other access rules

## 6. Security misconfiguration
- default system configuration (Apache, MySql, nginx etc)
- default features enablet that you don't need (just turn them off)
- default accounts with default password (admin/admin)
- displaying  default error pages (exact version of server software used, attacker may know vulnerabilities)

## 7. Cross-site scripting (XSS)
When the attaker manages to execute some malicious code in the context of the website in the user's browser.

## 8. insecure Deserealization

## 9. using components with known vulnerabilities
submit a description of the dependencies configured in your project to your default registry and ask for report of known vulnerabilities
```
npm audit  

npm audit fix  
```

## 10. Insufficient logging & monitoring
- the sustem experiences a data breach that nobody notices
- auditable vents are not logged
- access control failures, server side validation failures are not logged
- errors generate no? inadequate or unclear log messages
- logs are not monitored for suspicious activity
