
## Object that doest not has prototypes

```const obj2 = Object.create(null);
obj2.toString()
// Uncaught TypeError: obj2.toString is not a function
//    at <anonymous>:1:6 ```
