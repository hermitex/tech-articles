# Scope in JavaScript

Scope refers to the current context of javascript code execution.

This is where values and expressions are available or "visible" and can be referenced by the running program.

Values not visible or not available in the current execution context will **_NOT_** be available for use by your currently executing code.

Although scope can seem an easy concept to understand, in practice it sometimes trips even seasoned developers.

**NOTE**: Scope is normally hierarchically nested such that the child scope can reference the parent scope but the parent **_CANNOT_** reference the child scope.

In JavaScript, there are three types of scope and these include:

- The Global scope
  This is the default scope for any code that runs in script mode i.e everything runs line by line without any strict execution contexts
- The Module scope
  This scope occurs when code runs in module mode
- The Function scope
  As it suggests, this scope is created inside a function.

## Variables and Scope

In addition to the 3 scopes above, when variables are declared with ES6 syntax, `let` and `const`, a different scope is created:

- The Block scope
  This is the scope created within the body of a pair of curly brackets.

Note that the `var` keyword does not implement the block scope.

## Function Scope Example

```js
function functionScopeExample() {
  var name = "Anjette"; //=> available only within functioScopeExample() body

  console.log(name); //=> Anjette
}

functionScopeExample();

console.log(name); //=> ReferenceError: name is not defined
```

In the above snippet, we are not able to reference the `name` because its scope is limited to the `functionScopeExample` body i.e function scope.

The variable `name` is however successfully referenced within the function scope.

## Global Scope Example

Let us move the variable to a global scope:

```js
var name = "Anjette"; //=> available throughout the script i.e global scope
function globalScopeExample() {
  console.log(name); //=> Anjette
}

globalScopeExample();

console.log(name); //=> Anjette
```

In the above example, the variable has been declared in a global scope and thus it is available both inside the function and outside the function scope.

## Block Scope Example

A block is defined by a pair of curly brackets.

```js
{
  const name = "Anjette";
  // let name = "Anjette";
}
console.log(name); //=> ReferenceError: name is not defined
```

By using `const` or `let`, as shown in the snippet above, the variable `name` cannot be accessed outside the block. It is only accessible inside the block where it has been declared.

With the `var` keyword, the behavior is different.

```js
{
  var name = "Anjette";
}
console.log(name); //=> Anjette
```

Although the variable in the above snippet is declared in a block, the `var` keyword makes still available outside the block.

## Key Takeaways

- Scope defeines the extent to which variables are visible in a program
- There are 4 types of scopes in JS: global, function, module and, block.
