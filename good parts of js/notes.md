## Object that does not have any prototypes

```
const obj2 = Object.create(null);
obj2.toString()
// Uncaught TypeError: obj2.toString is not a function
//    at <anonymous>:1:6
```

## Check for NaN
```
NaN === NaN // false
isNan(NaN) // true
```

## regex visualizer 
https://jex.im/regulex/#!flags=&re=%5E(a%7Cb)*%3F%24

## 4 ways to invoke a function
- function form ``functionObject(arguments)``
- Method form ``thisObject.methodName(arguments)``
- Constructor form ``new FunctionObject(arguments)``
- Apply form ``functionObject.apply(thisObject, [arguments]``

## Meta Object API

```
Object.defineProperty(object, key, descriptor)
Object.definePropertires(object, object_of_descriptors)   

Object.getOwnPropertyDescriptor(object, key)
```
## Property descriptor
```
{
   get: function() {},
   set: function() {},
   configurable: false,
   value: bar,
   writabble: true,
   enumerable: true,
}
```
- value: any
- writable: boolean
- enumerable: boolean
- configurable: boolean
- get: function() {return value}
- set: function(value)

## object Extensibility
- Object.preventExtensions(object) //refuse to accept new properties
- Object.seal(object)
- Object.freeze(object) // makes every property readonly
  
