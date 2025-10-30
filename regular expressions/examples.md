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

## matching a word next to another word (allow 5 words between)
``/\b(?:words\W+(?:\w+\W+){0,5}together)|(?:together\W+(?:\w+\W+){0,5}words)\b/g``

## validating dates
``^(3[01]|[12][0-9]|0?[1-9)/(1[0-2]|0?[1-9])/([0-9]{2})?[0-9]{2}$``
