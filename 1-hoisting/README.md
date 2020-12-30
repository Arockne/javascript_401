# Part I: Hoisting

*Note: Before getting started on these exercises, please be certain that you've read through the root [README.md](../README.md) file in this repository.*

In order to complete these exercises, open [repl.it](https://repl.it/), choose JavaScript, and then write your code in the left-hand panel. You can run your code using the "Run" button.

### Two Forms of Functions

```js
// function declaration
function square(x) {
  return x * x;
}

// function expression
var square = function(x) {
  return x * x;
};
```

## Exercises

### Basic Requirements

#### Rewrite Functions

Rewrite the following *function declarations* using a *function expression*:

 ```js
 // 1.
 const cube = x => x * x * x;

 // 2.
 const fullName = (first, last) => first + " " + last;

 // 3.
 const power = (base, exp) => {
   if (exp === 0) {
     return 1;
   }
   return base * power(base, exp - 1);
 }

 // 4.
 const sumCubes = numbers => {
   var total = 0;
   for (var i = 0; i < numbers.length; i++) {
     total = total + cube(numbers[i]);
   }
   return total;
 }
 ```
#### Mechanics of Hoisting

Type out your best answers to the following questions:

1. Why does JavaScript output `undefined` instead of throwing an error in the following code?

  ```js
  console.log(message);

  var message = 'Hi there!';
  //Message outputs undefined because any binding assigned with the var keyword is hoisted to the top of its scope with the value of undefined

2. Why does JavaScript throw an error instead of logging `undefined` in the following code?

    ```js
    console.log(message);

    let message = 'Hi there!';
    //any binding that is assigned with the keyword let or const will result in an error because the binding is not initialized

3. Explain precisely what happens when the following code is executed.

    ```js
    console.log(showMessage());

    var showMessage = function(){
      return 'Hi there!';
    };
    //When the function is invoked above it will result in not a function because the anonymouse function is assigned in a function expression format

4. Why does JavaScript *not* throw any errors when the following code is executed?

  ```js
  console.log(showMessage());

  function showMessage(){
    return 'Hi there!';
  }
  //function declaration is hoisted to the its scope

#### Code Restructuring

Restructure the following instances of code to work correctly:

 ```js
 // 1.
 const values = [10, 20, 30];
 for(let i = 0; i < values.length; i++){
   console.log(values[i]);
 }

 ```
 ```js
 // 2.
 let lastLogin = '1/1/1970';
 
 const welcome = (first, last) => {
   return `Welcome, ${first} ${last}! You last logged in on ${lastLogin}.`
 };

 console.log(welcome('Charlie', 'Munger'));

 ```
