# Writable Objects Properties?

We all know how to create objects in JavaScript. For instance, if we can create a car object as follows:

```js
const car = {};
car.make = "Abarth 124 Spider Convertible 2017";
car.name = "Abarth";
car.price = "$28,195";

console.log(car);

/* =>
{
    "make": "Abarth 124 Spider Convertible 2017",
    "name": "Abarth",
    "price": "$28,195"
}
*/
```

In the above snippet, we have:

1. created an object using the object literal

1. added a property `make` and assigned it value corresponding to the car make

1. added a property `name` and assigned it a value of `Abarth`

1. added a property `price` and assigned it a value corresponding to the price of the car

This construct works just fine and as you can see, when we log the car object, we get back a nice car object.

## Writable & Non-writable Objects

Yeah, in JavaScript it is possible to dictate whether your object should be writable or not.

## How?

Let us see how this can be done. We will define the same object but in a slightly different way.

```js
const car = {};
Object.defineProperties(car, {
  make: {
    value: "Abarth 124 Spider Convertible 2017",
    writable: true,
  },
  name: {
    value: "Abarth",
    writable: true,
  },
  price: {
    value: "$28,195",
    writable: false,
  },
});

console.log(car);
/*=>
{
    "make": "Abarth 124 Spider Convertible 2017",
    "name": "Abarth",
    "price": "$28,195"
}
*/
```

In the above snippet we have:

1. created an object `car` using the object literal

1. used `Object.defineProperties()` methods to add properties i.e `make`, `name` and `price`.

When we log the `car` object, we get the same object as we did previously.

Looking closely, we can notice that the second syntax adds more details to our details.

As we can see, all our properties have a second attribute `writable` which takes a boolean value, `true` or `false`.

When the value of writable is `true`, we can modify that property i.e we can change its value.

However, when the value of writable is `false`, we cannot modify that value.

## Let Us Check it Out

First of all, we are going to modify the first object.

```js
const car = {};
car.make = "Abarth 124 Spider Convertible 2017";
car.name = "Abarth 124";
car.price = "$28,195";

console.log(car);
/*=>
{
    "make": "Abarth 124 Spider Convertible 2017",
    "name": "Abarth 124",
    "price": "$28,195"
}
*/

// Modifying properties
const car = {};
car.make = "Abarth 595 Competizione Convertible 2016";
car.name = "Abarth 595";
car.price = "$28,095";

console.log(car);
/*=>
{
    "make": "Abarth 595 Competizione Convertible 2016",
    "name": "Abarth 595",
    "price": "$28,095"
}
*/
```

As you can see, we have been able to modify the properties of the `car` object.

Let us now see the how the second car objects behaves when the writable property is added.

```js
const car = {};
Object.defineProperties(car, {
  make: {
    value: "Abarth 124 Spider Convertible 2017",
    writable: true,
  },
  name: {
    value: "Abarth",
    writable: true,
  },
  price: {
    value: "$28,195",
    writable: false,
  },
});

console.log(car);
/*=>
{
    "make": "Abarth 124 Spider Convertible 2017",
    "name": "Abarth 124",
    "price": "$28,195"
}
*/

// Modifying properties
car.make = "Abarth 595 Competizione Convertible 2016";
car.name = "Abarth 595";
car.price = "$28,095";

console.log(car);
/*=>
{
    "make": "Abarth 595 Competizione Convertible 2016",
    "name": "Abarth 595",
    "price": "$28,195"
}
*/
```

If you look closely, you will notice that we have been able to change the value of `make` and `name`.

However, we were not able to modify the value of `price`. This is possible because the value of `writable` is set to `false`. The rest have been set to `true` allowing them to be modified.

## Key Takeaways

1. Objects can be created using object literals and have its properties and values populated with a `dot` notation

1. Object created as described in `1` above are modifiable

1. We can also populate properties to an object using `Object.defineProperties()` method

1. The approach defined in `3` above allows you to define whether or not the object properties are modifiable
