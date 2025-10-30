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

## Repetitions 
`` + `` - matches one or more occurrences   
`` ? `` - matches zero or one occurrences   
`` * `` - matches zero or more occurrences  
`` *? `` - lazy repetition (as less characters as possible)
goes after a symbol or a group

## Repetition amount
``{min,max}`` - matches min to max occurrences
``{num}`` - matches exect num occurrences
``{min,} - matches min or more occurrences

## Anchored expressions
``^`` - anchors the match to the start of the line (works for each line with m flag)       
``$`` - anchors the match to the end of the line (works for each line with m flag)    
``\b`` - word boundary - pattern bounded by a non-word character   
``\B`` - Nonword boundary - pattern bounded by a word character   
`` /\bplan\b/g`` - matches plan but not plant (only full word)
`` /plan\B/g`` - matches plant or planet but not plan

## | - Specifying options
``/\bmonday|turesday|wednesday|thursday|friday|saturday|sunday\b/ig``   

## () - Grouping
``/([a-d][1-5]){5}/g`` - matches b1d2a3b4c5    
``/\b(monday|turesday|wednesday|thursday|friday|saturday|sunday)\b/ig``

## reusing Groups \1
we can detect repetitive groups inside the text   
``/(yo)\1/g``   - matches yoyo    
``/^(\d\d\d\d)[-./](\d{1,2})[-./]\)$/g`` - reference to group should have the same text inside (2018-9-9 but not 2018-9-08)    
``/^(\d\d\d\d)([-./])(\d{1,2})\2(\d{1,2})$/g``    
``/^(?:\d\d\d\d)([-./])(\d{1,2})\1(\d{1,2})$/g``  - making group non capturing (without index) by using ``?:``   

## (?=) Lookahead groups
``/\w+(?=\.com)/g`` - lookahead group (?=\.com)       
password check regex - ``^/(?=.{8,})(?=.*[A-Z])(?=.*[a-z])(?=.*[0-9]).*$/g`` - contains number, uppercase, lowercase, more that 8 symbols

## (?!) Negative lookahead Group
``^/(?=.{8,})(?=.*[A-Z])(?=.*[a-z])(?!.*[0-9]).*$/g`` - this string could not include any number  ``(?!.*[0-9])``

## representing unicode symbols
``\u0065``   

## ES6 Unicode (more than 4 symbols to represent) \u1D11E
need to use u-flag for support   
``/\u{1D11E}/u``
