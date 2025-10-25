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
