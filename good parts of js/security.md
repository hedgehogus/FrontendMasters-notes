# principles

## Deterrence (horrifications) is not effective
You can't punish an invisible attacker.   
prevention is only efective machanism

## There is no security in the obscurity (The kerckhoffs Principle)
The design of a system should not require secrecy. And compromise of the system should not inconvenience the correspondents    
The more secrets you have the harder they are to keep   

**One Time Pad**
- the key must always remain secret
- The key must be at least as long as the plain text
- the cypher text is obtained by xor of the plain text and the key
- the key must be perfectly random
- a key must never be used more than once

## False security is worse than no security
Unnecessary expense and confusion of risk

### Cross Site Scripting (XSS)
## why is there
- too many languages in the web stack, each with ot's own encoding, quoting, commenting and escapement convetions
- each can be nested inside of each other
- browsers do heroic things to make sense of malformed content
- template-based web frameworks are optimized for xss injections
- the javascript global object gives every scrap of script the same set of powerful capabilities
- as bad as it is at security, the browser is vast improvement over everithing else
