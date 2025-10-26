## metacharacters
^$.*?=!:|\/()[]{}

## . - wildcard
. - represents any single character with exceptions of some characters like newline
```
/h.t/g
```
matches 'hot', ' hat', 'h t', 'h@t', 'h  t'(with tab) etc

## \ - escaping metacharacters 
```
/h\.t/g
```
matches 'h.t'

``\\`` - escaping backslash

## control characters
- ``\t`` - tab
- ``\v`` - vertical tab
- ``\n`` - newline
- ``\r`` - carriage return     
newline or carriage return symbol using depends on the system (mac or windows)

## [] - character sets
``` /gr[ae]y/```   
maches 'gray', 'grey', but not 'graey'
```/[abcd]/``` only matches one of this letters

## Specifying a Range (-)
```/[1-4]/``` matches 1 2 3 4      
```/[\-.]/``` matches - and .    
```/[a-e]/``` range of letters   

## ^ - Excluding a character Set 
```/0x[^0-9A-F][^0-0A-F]/``` excluding all set 0-9A-F   
^ should go the first character after [

## Shorthand for character sets
- ``\d [0-9]`` - digit
- ``\w [a-zA_Z0-9_]`` - word
- ``\s [ \t\r\n]`` - space
- ``\D [^0-9]`` - not digit
- ``\W [^a-zA_Z0-9_]`` - not word
- ``\S [^ \t\r\n]`` - not space
