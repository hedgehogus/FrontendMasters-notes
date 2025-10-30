## Email address
``^[^\s@]+@[^\s@.]+\.[^\s@.]+$``

## Matching a twitter name
``^(?=@)\w+$``

## Testing Passwords
``^.{8,32}$`` - length   
``[^0-9A-Za-z]`` - special characters (or just a list of them)

## Swap first and last name
```
const name = "Smith, James"
name.replace(/(\w+), (\w+)/, "$2 $1")
```
