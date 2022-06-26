# Implementing PrivateFields in JavaScript

Just until recently, JavaScript did not offer a way for programmers to define private fields.

> A private field is a class property whose access is limited to within the class. These properties can not even be inherited by sub-classes.

To symbolize private fields, one had to write something that looks like this:

```js
class Employee {
  constructor(salary, age) {
    this._salary = salary;
    this._age = age;
  }
}
```

In the above code snippet, the `'_'` before `salary` and `age` were used to inform other programmers that these fields are private and are not meant to be accessed externally.

## Wait! We can still access these fields externally

```js
const employee = new Employee(20000, 35);
employee._salary;
// => 20000

employee._age;
// => 35
```

As we can see, this workaround does not change the behavior of the `_salary` and `_age` since they can still be accessed and or modified externally.

Simply said, the `_salary` and `_age` are still publicly accessible.😒

## Private Fields

Recently, JavaScript has introduced private fields. Now, we can concisely define private fields and sleep comfortably well assured that someone will not accidentally access and modify them externally.

## How does this look like?

To define private fields, this is what you need to do:

```js
class Employee {
  // We must declare private fields before accessing them
  #salary;
  #age;

  constructor(salary, age) {
    this.#salary = salary;
    this.#age = age;
  }
}
```

Yes! It is that simple! The `#` indicates that this is a private property. Unlike the `_`, the `#` restricts any external access to `salary` and `age` properties.

Trying to access these properties externally will return `undefined`.

```js

const employee = new Employee(20000, 35);
employee.#salary;
// => undefined

employee.#age;
// => undefined
```

Oh nice! Now we have achieved the intended behavior.
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/pje66se79ou4ilxr0idc.gif)
 
## What else should I be Aware of?

Well, there are a few things that you need to take note when declaring private properties using the `#` operator.

While the code below will work just fine:

```js
class Employee {
  constructor(salary, age) {
    this._salary = salary;
    this._age = age;
  }
}
```

This one 👇 will not work:

```js
class Employee {
  constructor(salary, age) {
    this.#salary = salary;
    this.#age = age;
  }
}
```

## Why?

When using `#` to define a property, that properly must be declared before being accessed.

In other words, it is not a must to declare public fields before accessing them but you _MUST_ declare private fields before accessing them.

## Key Takeaways

- Private fields are properties not accessible externally.
- In JavaScript, private fields are declared by appending `#` just before the property name e.g `#privatePropertyName`.
- Accessing private fields externally will return `undefined`
- Private fields must be declared before being accessed.
