## Same origin Policy
An origin in web security/networking is the unique combination of a **protocol** (scheme), **domain** (hostname), and **port** that identifies a web resource

## allow cross origin requests
Set header **Access-Control-Allow-Origin: https://allowed.origin**

## CORS
Cross origin resourse sharing
```
app.use(cors({origin: 'http://where.request.comes.from'}));
```

## Content Security Policy
cdn - content delivery network

limit the origins that we trust and allow to execute in the context of the website

Options for Content Security Policy
- origin
- self
- none
- hash
- nonce (number used only once) pseudo random
- unsafe-inline  

**header:**
Content-Serucrity-Policy: \<directive> '\<origin>'  
`` Content-SecurityPolicy: default-src 'self'``   
`` Content-SecurityPolicy: img-src 'self'``   
`` Content-SecurityPolicy: font-src 'self'``   
`` Content-SecurityPolicy: script-src 'self'``   
`` Content-SecurityPolicy: style-src 'self'``   

## Subresource Integrity
```
<script src="http://some.external.origin"   
  integrity="sha256_XXX"   
  crossorigin="anonymous"   // - dont send cookies to thos origin
>
</script>
```
