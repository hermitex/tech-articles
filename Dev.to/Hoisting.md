# Hoisting in JavaScript

JavaScript is treacherous in many confusing ways and **hoisting** is just one of those things that tripped me a lot when I started learning and writing JavaScript.

In JavaScript, hoisting is a phenomenon where the JavaScript interpreter behaves as if it lifts the declarations of variables, functions and classes to the top of their scope before their execution. If you think about it, it means that JavaScript makes these declarations available for use before their existence.

## Variable Hoisting

Variables are hoisted but they are initialized with a value of `undefined` by default instead of the actual value you have assigned them.

This is, however, only possible with the `var` keyword. Trying to use access variables declared with `let` or `const` before they exist will result in JS throwing a ReferenceError.

Let us have a look at these behaviours:

```js
console.log(name); //=> undefined
var name = "Anjette";
```

In the snippet above, we are trying to access a variable `name` declared with the `var` keyword.

Although the variable has been assigned the value of `Anjette`, we get `undefined` instead. Why?

This is because the variable is being hoisted but its initialization is not. Instead, JS assigns it a default value, `undefined`.

The code above is equivalent to the following example:

```js
var name; // default value is `undefined
console.log(name); //=> undefined
name = "Anjette";
console.log(name); //=> Anjette
```

Hoisting with the `let` or `const` syntax shows different behaviour. Let's look at the example below:

```js
console.log(name); //=> ReferenceError: Cannot access 'name' before initialization
let name = "Anjette";
```

In the above example, we have the variable declared with the `let` keyword. When we try to access it before the declaration, we get a ReferenceError.

Although the variable is hoisted, unlike the variable declared with the `var` keyword, it is not assigned the default value of `undefined`.

And that is why we get the ReferenceError instead of the default value of `undefined`.

For the same reason, the variables declared with the `const` keyword will behave the same as those with `let`.

When it comes to functions, hoisting makes it possible to access and safely use functions before they are declared or "exist".

## Hoisting in Functions

```js
//=> Access function before declaration
sayHello(); //=> Hello

//=> Function after declaration
function sayHello() {
  console.log("Hello");
}
```

Note that the code above does not cause any errors. Instead, it executes successfully giving us the expected result.

This is because the function declaration has been moved to the top of its declaration i.e hoisted.

However, function expressions do not have the privilege of using this hoisting effect. Let us see how the function expression behaves.

### Function expression with `let`

Trying to access a function expression before it exists will cause JS to throw a ReferenceError.

```js
//=> Access function before declaration
sayHello(); //=> ReferenceError: Cannot access 'sayHello' before initialization

console.log(sayHello); //=> ReferenceError: Cannot access 'sayHello' before initialization

//=> Function after declaration
let sayHello = function () {
  console.log("Hello");
};
```

In the snippet above, `sayHello()` cannot be accessed because it is a function expression. Furthermore, the `let` keyword further restricts hoisting. The reason for the ReferenceError is because of the way hoisting behaves with the `let` or `const` keyword as discussed above.

### Function expression with `var`

```js
//=> Access function before declaration
sayHello(); //=> TypeError: sayHello is not a function
console.log(sayHello); //=> undefined
//=> Function after declaration
var sayHello = function () {
  console.log("Hello");
};
```

With the `var` keyword, the variable name `sayHello` is hoisted, but its initialization is not. SayHello has a value of `undefined` before its initialization which is set by JS. That is why we see a TypeError when trying to invoke the function.

```js
// => Access the variable name
console.log(sayHello); //=> undefined

//=> Function after declaration
var sayHello = function () {
  console.log("Hello");
};
```

## What about classes?

Just like their cousins, functions, and classes are also hoisted and thus their references can be accessed before their declaration.

However, similar to variables declared with `let` or `const`, they are not initialized and thus trying to use the hoisted class causes JS to throw a ReferenceError.

class expressions i.e when a class is assigned to a variable, the variable will be hoisted but its initialization will not be hoisted.

## Key Takeaways

- Hoisting is the behaviour where the JavaScript interpreter lifts declarations to the top of the program
- A variable declared with the `var` keyword is hoisted but initialized with a default value of `undefined`.
- Variables declared with the `let` or `const` keyword are hoisted but are not initialized with a default value of `undefined`. Thus access them before initialization throws a ReferenceError.
- Hoist makes functions, variables and classes available before their declaration
- Functions declared with the function keyword are hoisted and can be safely used before their declarations.
- Function expressions are not hoisted. However, the variables assigned to them are hoisted.
- Classes are also hoisted but they are not initialized.
