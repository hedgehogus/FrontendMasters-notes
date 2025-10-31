## two ways to create regex
```
let regex1 = new RegExp('hello');
let regex2 = /world/;
```    
## regex1.test(txt)
```
let regex1 = /world/;
let txt = 'hello world';
regex1.test(txt) //true
```   
check if pattern that we created matches the text. If this pattern/text is fount within the string

## regex1.exec(txt)
```
let regex1 = /world/;
let txt = 'world hello world';
regex1.exec(txt) // ['world', index: 6, input: 'hello world', groups: undefined]
```   
returns array of actual match (array has capturing groups inside)

### iterating over matches with regex object
```
while(match = regex.exec(phrase)) {
  if (match.index == regex.lastIndex) {
    regex.lastIndex++;
  }
  console.log(match)
}
```

## regex.toString()
returns a string of the redular expression syntax
```
let regex1 = /world\s/;
regex1.toString(); //  '/world\\s/'
```

## txt.match(regex1)
```
let regex1 = /world/;
let txt = 'world hello world;
txt.match(regex1) // ['world', 'world']
```   
returns array of actual matches

## txt.search(regex1)
```
let regex1 = /world/;
let txt = 'world hello world;
txt.search(regex1) // 0
```   
returns index of first match

## txt.replace(regex1)
```
let regex1 = /world/;
let txt = 'world hello world;
txt.replace(regex1, 'hola') // 'hola hello hola'
```
returns new string with replaced parts

## txt.split(regex1)
```
let regex1 = /hello/;
let regex2 = /\s/;
let txt = 'world hello world';
txt.split(regex1) // ['world ', ' world']
txt.split(regex2) // ['world', 'hello', 'world']
```
returns splitted array of strings
