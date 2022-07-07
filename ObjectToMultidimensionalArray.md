# Create Multidimensional Array from an Object

## Did you know that you can create a multidimensional array from an object?

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1ok2tb9ewb0c5yic44cu.gif)

In this short tutorial, we are going to see how we can achieve that.

First, let us assume we have an object that looks like this:

```js
const cart = {
  phone: {
    brand: "Techno Camon 18",
    price: "Sh. 25000",
  },
  shoes: {
    brand: "Oxford",
    price: "Sh. 18000",
  },
  jeans: {
    brand: "Levis",
    price: "Sh. 2000",
  },
};
```

The above snippet, we have an object called `cart` with three keys corresponding to a product. Each of these keys hold a object as a a value.

The value for each of the objects contains two properties, a `brand` and `price`.

Great! Now what we want is to come up with a multidimensional array of this object, `cart`.

## Let us do it

```js
let cartAsArray = Object.entries(cart);

console.log(cartAsArray);
/* => [
    [
        "phone",
        {
            "brand": "Techno Camon 18",
            "price": "Sh. 25000"
        }
    ],
    [
        "shoes",
        {
            "brand": "Oxford",
            "price": "Sh. 18000"
        }
    ],
    [
        "jeans",
        {
            "brand": "Levis",
            "price": "Sh. 2000"
        }
    ]
]*/
```

In the above snippet, we have used `Object.entries()` method to convert the object, `cart` into a multidimensional array.

As you can see, we have three arrays, each with two elements. The first element is the item name and the second element is an object containing the brand and the price.

## Use Case

In the case where you want to loop through the object, one can easily use the `for...in` loop which iterates through the object keys.

However, in the case where you could like to order the items in a certain way, `Object.entries()` can be very helpful..

Let us say for instance we want to order our cart items in alphabetical order.

This can be done this way:

```js
let orderedCartItems = Object.entries(cart).sort();
console.log(orderedCartItems);
/* => [
    [
        "jeans",
        {
            "brand": "Levis",
            "price": "Sh. 2000"
        }
    ],
    [
        "phone",
        {
            "brand": "Techno Camon 18",
            "price": "Sh. 25000"
        }
    ],
    [
        "shoes",
        {
            "brand": "Oxford",
            "price": "Sh. 18000"
        }
    ]
] */
```

## That is nice

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hl0t2mxlrt3w1oaatj3l.gif)

As you can see, by invoking the `Array.prototype.sort()` method on the multidimensional array, we are able to sort the cart items alphabetically and in ascending order.

## What if I want my object back?

There are cases where you would want to have the object back. I get that and here is how you can maneuver.

```js
cart = Object.fromEntries(orderedCartItems);
console.log(cart);
/* => {
    "jeans": {
        "brand": "Levis",
        "price": "Sh. 2000"
    },
    "phone": {
        "brand": "Techno Camon 18",
        "price": "Sh. 25000"
    },
    "shoes": {
        "brand": "Oxford",
        "price": "Sh. 18000"
    }
}
*/
```

Did you see that? Yeaah we got the object back but this time round it is ordered alphabetically.

While I know you can have creative ways to use this methods, the example provided above is just for demonstration.

## Key Takeaways

- We can turn an object into a multidimensional array using `Object.entries()` method

- We can revert back to the object by calling `Object.fromEntries()` on the multidimensional array

## In which cases do you think you can find this useful?
