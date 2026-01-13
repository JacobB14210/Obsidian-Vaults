- Being able to use an interpreter to move declaration of functions, variables, or classes to the top of scope, prior to execution of the code

```js
function hoist() {
  a = 20; // Declared as a global variable when function is called
  var b = 100;
}

hoist();

console.log(a); 
/* 
Accessible as a global variable outside hoist() function
Output: 20
*/

console.log(b); 
/*
Since it was declared, it is confined to the hoist() function scope.
We can't print it out outside the confines of the hoist() function.
Output: ReferenceError: b is not defined
*/
```