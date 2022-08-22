# Arrays and Array Methods in JavaScript

## Table of Content

## What is an Array

In JavaScript, an array is an `object` and not a primitive data type that allows one to store collections of items in one variable.g

## Core Characteristics of Arrays

- Arrays are zero-indexed. This means the first element of an array will be at index `0` and the last element will be at the length of the array minus `1`.

- Arrays in JavaScript are flexible. This means they can grow or shrink in size as opposed to being rigid to the initially declared size.

- Arrays in JavaScript are not associative, i.e, they do not appear in key-value format and thus can only be accessed by their indices.

- Copy operations on JavaScript arrays will only create shallow copies and not deep copies.

## The Array Constructor

Array objects are created in JavaScript by invoking `Array()` which is the array constructor.

## Array Properties

### Array.prototype.length

Every array instance has the `length` property which when invoked returns a number equal to the length of the array which is equivalent to the total number of elements in the array.

Let us see the property in action:

```js
// Declare the array and assign 3 elements
let myArray = ["John", "Lucy", "Anjette"];

// Get the array length and save
let arrayLength = myArray.length;

//Print to the console the array length
console.log(arrayLength);
// => 3
```

## Array Methods

JavaScript arrays has several methods. Let us get to know them!

### Array.prototype.at()

This method takes in one argument, a number, which should correspond to the position of an element in the array. When called on an array object, it returns an array element at the given index. It can take in negative numbers to indicate that you are counting from back of the array.

Let us have a look at how it works:

```js
// Declare the array and assign 3 elements
let myArray = ["John", "Lucy", "Anjette"];

// Get the array element at index 1
let elementAtIndexOne = myArray.at(1);

//Print to the console the array length
console.log(elementAtIndexOne);
// => Lucy
```

Let us try to pass a negative index:

```js
// Declare the array and assign 3 elements
let myArray = ["John", "Lucy", "Anjette"];

// Get the array element at index -1
let elementAtIndexOne = myArray.at(-1);

//Print to the console the array length
console.log(elementAtIndexOne);
// => Anjette
```

### Array.prototype.concat()

This method takes in at least one argument -array(s) and or value(s)- and returns a new array which is the result of the combination of the array the method was called on and the passed in array(s) and or value(s).

Here is the `concat` at work:

```js
// Declare the array and assign 3 elements
let myArray = ["John", "Lucy", "Anjette"];
let smallArray = ["Mariam"];

//Print to the console the array before joining
console.log(myArray);
// => ['John', 'Lucy', 'Anjette']

// Join arrays
let newArray = myArray.concat(smallArray);

//Print to the console the array after joining
console.log(newArray);
// => ['John', 'Lucy', 'Anjette', 'Mariam']
```

### Array.prototype.entries()

When invoked on an array object, this method returns a new array iterator consisting key/value pairs for all elements in the array. The key will be the index and the value is the actual element at that index.

Here is the method in action:

```js
// Declare the array and assign 3 elements
let myArray = ["John", "Lucy", "Anjette"];

// Get the entries
let arrayEntries = myArray.entries();

//Print to the console the array
console.log(arrayEntries);
// => Array Iterator {  }
```

Here is what we mean:

```js
let nextElement = arrayEntries.next().value;
console.log(nextElement);
// => Array [ 1, "Lucy" ]
```

### Array.prototype.every()

The `every()` method returns a Boolean value, `true`, when all elements in the array on which the method was invoked fulfills the testing condition.

Here is how it works:

```js
// Declare the array and assign 4 elements
let myNumbers = [-1, -3, -7, -2];

// Define a testing condition
const numberIsNegative = (number) => number < 0;

// Get the entries
let result = myNumbers.every(numberIsNegative);

//Print to the console the result
console.log(result);
```

The method returns `false` if the condition fails. Here is an output after flipping the sign of the last element to positive:

### Array.prototype.fill()

This method will populate an array object from the first to the last index with a static value.

Her is how it works:

```js
// Declare the array and assign 4 elements
let mySuperHero = ["Wat", "Man", "Wonder", "Woman"];

// Fill with 'WatMan' from index 1 to index 4
let populatedSuperHero = mySuperHero.fill("WatMan", 1, 4);

//Print to the console the result
console.log(populatedSuperHero);
// => ['Wat', 'WatMan', 'WatMan', 'WatMan'];
```

### Array.prototype.filter()

This methods returns a modified array consisting of all elements that pass a testing condition i.e the "filter".

Her is how it works:

```js
// Declare the array and assign elements
let myNumbers = [1, 8, 3, 7, 2, 4, 96, 57];

// Fill out out only even numbers
let evenNumbersOnly = myNumbers.filter((number) => number % 2 == 0);

//Print to the console the result
console.log(evenNumbersOnly);
// => [8, 2, 4, 96];
```

### Array.prototype.findIndex()

When called on an array object, this method returns the first element that fulfills the testing condition. It returns `-1` if there is no element in the array that satisfies the condition.

Here is how it works:

```js
// Declare the array and assign elements
let myNumbers = [1, 3, 3, 7, 2, 4, 96, 57];

// Find index of number === 3
let index = myNumbers.findIndex((number) => number === 3);

//Print to the console the result
console.log(index);
// => 1;
```

## Array.prototype.flat()

This method, when invoked on an array object, it returns a new array object with all nested arrays concatenated into the the parent array up to the depth specified.

Here is how it works:

```js
// Declare the array and assign elements
// We have [3, 7, 2, 4] and [57] as nested arrays
let myNumbers = [1, 3, [3, 7, 2, 4], 96, [57]];

// Flatten the array
let flattenedArray = myNumbers.flat();

//Print to the console the result
console.log(flattenedArray);
// => [1, 3, 3, 7, 2, 4, 96, 57];
```

Let us try with a more deeper nested array

```js
// Declare the array and assign elements
// We have [3, 7, 2, 4] and [57] as nested arrays
let myNumbers = [1, 3, [[[3, 7, 2, 4]]], 96, [57]];

// Flatten the array
let flattenedArray = myNumbers.flat(3);

//Print to the console the result
console.log(flattenedArray);
// => [1, 3, 3, 7, 2, 4, 96, 57];
```

## Array.prototype.forEach()

This method executes a callback fuction once for each iteration.

```js
// Declare the array and assign elements
let myNumbers = [1, 3, 3, 7];

//Print each number to the console
myNumbers.forEach((number) => console.log(number));
// => 1
// => 3
// => 3
// => 7
```

You can also access the index of the current element by passing the second argument to the callback function:

```js
myNumbers.forEach((number, index) => console.log(number));
```

## Array.prototype.flatMap()

This method returns a new array object after applying a callback function to each of the element in the array. The result is then flattened down by one level.

```js
// Declare the array and assign elements
let myNumbers = [1, 3, 3, 7, 2, 4];

// Get the new array
let newArray = myNumbers.flatMap((number) => [number, number / 2]);

//Print to the console the result
console.log(newArray);
//=> [1, 2, 3, 6, 3, 6, 7, 14, 2, 4, 4, 8];
```

This method is identical to `map()` followed by `flat()` of depth 1.

## Array.prototype.includes()

This method takes one argument, an element, and then returns `true` if the element given exists in the array object on which it is called.

```js
// Declare the array and assign elements
let myNumbers = [1, 3, 3, 7, 2, 4, 96, 57];

// Get the new array
let elemIsMember = myNumbers.includes(4);

//Print to the console the result
console.log(elemIsMember);
// => true;
```

If the element is not a member of the array, it returns `false`.

```js
// Declare the array and assign elements
let myNumbers = [1, 3, 3, 7, 2, 4, 96, 57];

// Get the new array
let elemIsMember = myNumbers.includes(-4);

//Print to the console the result
console.log(elemIsMember);
// => false;
```

## Array.prototype.indexOf()

This method returns the index of the first element that fulfills matches the passed in element.

Here is how it works:

```js
// Declare the array and assign elements
let myNumbers = [1, 3, 4, 3, 7, 2, 4, 96];

// Get the new array
let indexOf = myNumbers.indexOf(4);

//Print to the console the result
console.log(indexOf);
// => 2;
```

You can also pass in the index at which to such from as the second argument:

```js
// Declare the array and assign elements
let myNumbers = [1, 3, 4, 3, 7, 2, 4, 96];

// Get the new array
let indexOf = myNumbers.indexOf(4, 3);

//Print to the console the result
console.log(indexOf);
// => 6;
```

It return `-1` if the element is not a member of the array:

```js
// Declare the array and assign elements
let myNumbers = [1, 3, 4, 3, 7, 2, 4, 96];

// Get the new array
let indexOf = myNumbers.indexOf(-4);

//Print to the console the result
console.log(indexOf);
// => -1;
```

**NOTE:**

1. The index to search from is optional

1. If the index given is greater than the length of the array, the method will return `-1` indicating the array cannot be searched

1. If a negative index is passed, the array will still be searched from front to back

1. If no index is provided, the default index, `0`, is used and thus the entire array is searched from index `0` to `array.length - 1`

1. The `indexOf()` uses the strict comparison (`===`) to compare the elements to be searched and the target element.

## `Array.prototype.isArray()`

This method returns takes in one argument and returns `true` is the value of the argument evaluates to an array.

Here is how it works:

```js
// Declare the array and assign elements
let myNumbers = [1, 3, 4, 3, 7, 2, 4, 96];

// Get the new array
let isArray = myNumbers.isArray(myNumber);

//Print to the console the result
console.log(isArray);
// => true;
```

It returns `false` if the value of the arguments evaluates to a non-array object.

```js
// Declare the array and assign elements
let myNumbers = "Not an Array!";

// Get the new array
let isArray = myNumbers.isArray(myNumber);

//Print to the console the result
console.log(isArray);
// => false;
```

## Array.prototype.join()

This method returns takes in one optional argument, a separator/delimiter, and returns concatenated values consisting of the array elements it was called upon separated with the the provided separator.

Here is how it works:

```js
// Declare the array and assign elements
let words = ["I", "want", "to", "learn", "JavaScript."];

// concatenate the array, separating each element with a space (" ")
let sentence = words.join(" ");

//Print to the console the result
console.log(sentence);
// => I want to learn JavaScript.;
```

If no separator is provided, the output is separated by a comma, `","`

```js
// Declare the array and assign elements
let words = ["I", "want", "to", "learn", "JavaScript."];

// concatenate the array
let sentence = words.join();

//Print to the console the result
console.log(sentence);
// => I,want,to,learn,JavaScript.;
```

## Array.prototype.keys()

When invoke on an array, the `keys()` method returns an Array iterator consisting of the keys correcsponding to each of the indices of the elements in the array.

Here is an example:

```js
let nums = [1, 2, 3, 4, 5];
let num_keys = nums.keys();
for (const key of num_keys) {
  console.log(key);
}
// => 0
// => 1
// => 2
// => 3
// => 4
```

## Array.prototype.lastIndexOf()

This method returns the last index at which a given element can be found. If the array does not contain the given element, it returns `-1`.

Note that this methods iterates over the elements in the array from the last index backwards.

```js
let nums = [4, 1, 2, 3, 4, 5];
let last_index_of_4 = nums.lastIndexOf(4);
console.log(last_index_of_4);
// => 4
```

In the above snippet, the target element is at index 1 as well as index 4. However, the `Array.prototype.lastIndexOf()` method returns the last index, 4, of the element since it counts from the back of the array.

## Array.prototype.map()

The map method returns a new and transformed array consisting of all the elements of the array it was called on. The method takes in as the first argument a callback function that is called once for each iteration in order. The callback function is never invoked for indices whose elements have been deleted or not yet set.

Since the map method creates a new array, avoid using this method in case you are not going to use the generated array. Instead, consider using more generic functions like `Array.prototype.forEach()` or `for...of`.

The best use case for `Array.prototype.map()` is when you want to iterate over all the element of an array and make modifications without altering the original array.

Here is an example:

```js
let nums = [1, 2, 3, 4, 5];
let nums_doubled = nums.map((num) => num * 2);
console.log(nums);
// => [1, 2, 3, 4, 5];
console.log(nums_doubled);
// => [2, 4, 6, 8, 10];
```

## Array.prototype.of()

This method creates a new an array instance containing the number of arguments given to it.

Here is an example:

```js
let nums = Array.of(10);
console.log(nums);
// => [10];
```

Notice that unlike the `Array` constructor, the `Array.prototype.of()` method created an array with only one element, 10. The constructor, on the other hand could have created a new array with 10 undefined elements.

Here is an example:

```js
let num = Array.of(5);
console.log(num.length);
// => 1;

let nums = Array(10);
console.log(nums.length);
// => 10
```

## Array.prototype.pop()

This method destructively removes an element from the end of the array thus changing the length of the array. The method returns the removed element or `undefined` if the array is empty.

```js
let nums = [1, 2, 3, 4, 5];
let removed_element = nums.pop();
console.log(removed_element);
// => 5
console.log(nums);
// => [1, 2, 3, 4]
```

## Array.prototype.push()

This method destructively adds one or more elements to the end of the array thus changing the length of the array. The method returns the new length of the array on which it was invoked.

```js
let nums = [1, 2, 3, 4, 5];
let new_nums_len = nums.push(6);
console.log(new_nums_len);
// =>  6
console.log(nums);
// => [1, 2, 3, 4, 5, 6]
```

## Array.prototype.reduce()

The methods executes a callback function for each iteration in order and returns a single value that summarizes the entire array on which it as called on.

The callback function takes two arguments: the previous value and the current value. If the initial value is not provided, the element at index 0 of the array is used as the initial value.

While the reduce function can be used on any array object, the simplest way to use the method is by summing up an array of numbers.

Here is an example:

```js
let nums = [1, 2, 3, 4, 5];
let sum_of_nums = nums.reduce(
  (previousValue, currentValue) => previousValue + currentValue,
  0
);
console.log(sum_of_nums);
// =>  15
```

In cases where you need to use `Array.prototype.filter()` and `Array.prototype.map()` i.e `Array.filter.map`, it is advised to use `Array.prototype.reduce()` to achieve your desired functionality. This is more efficient since `Array.prototype.map()` iterates over the array twice which is too expensive.

Overall, if your use case neither fits in `Array.prototype.prototype.map()` nor `Array.prototype.filter()`, consider using `Array.prototype.reduce()`.

## Array.prototype.reduceRight()

This method walks through each element of the array from right to left reducing it to a single value. It takes a callback function as the first argument which takes in two arguments: `accumulator` and `currentValue`.

Here is an example:

```js
let nums = [
  [1, 2],
  [3, 4],
];
let nums_right_left = nums.reduceRight((accumulator, currentValue) =>
  accumulator.concat(currentValue)
);
console.log(nums_right_left);
// =>   [ 3, 4, 1, 2 ]
```

## Array.prototype.reverse()

The method destructively reverses the order of array elements it is invoked on **_in place_**.

> In computer science, an **_in place_** algorithm refers to a procedure that transforms an input by the help of auxiliary data structures. Typically, the inputs is overwritten by the output as the procedure is executing.

Here is an example:

```js
let nums = [1, 2, 3, 4];
let reversed_nums = nums.reverse();

console.log(reversed_nums);
// =>   [ 4, 3, 2, 1]
```

## Array.prototype.shift()

This method destructively removes an element from the beginning of the array thus changing the length of the array. The method returns the removed element or `undefined` if the array is empty.

```js
let nums = [1, 2, 3, 4, 5];
let removed_element = nums.shift();
console.log(removed_element);
// => [2, 3, 4, 5]
```

## Array.prototype.slice()

This method non-destructively creates a shallow copy of an array containing elements from the original array starting from the start index to the end index, end index excluded.

```js
let nums = [1, 2, 3, 4, 5];
let sliced_nums = nums.slice(0, 2);
console.log(sliced_nums);
// => [1, 2]

// The original array won't be modified
console.log(nums);
// => [1, 2, 3, 4, 5]
```

If only one argument is provided, the slice will copy all the elements from the index provided up to end of the array.

```js
let nums = [1, 2, 3, 4, 5];
let sliced_nums = nums.slice(2);
console.log(sliced_nums);
// => [3, 4, 5]
```

If no argument is provided, the slice method simply copies everything over to a new array.

```js
let nums = [1, 2, 3, 4, 5];
let sliced_nums = nums.slice();
console.log(sliced_nums);
// => [1, 2, 3, 4, 5]
```

Note that providing a negative index will have an effect of `slice`ing from the back of the array.

```js
let nums = [1, 2, 3, 4, 5];
let sliced_nums = nums.slice(-2);
console.log(sliced_nums);
// => [ 4, 5 ]
```

Whereas providing a non-existing index will return an empty array:

```js
let nums = [1, 2, 3, 4, 5];
let sliced_nums = nums.slice(6);
console.log(sliced_nums);
// => []
```

## Array.prototype.some()

This method tests of any member of an array it is invoked on passes a given condition. It takes in a callback function which executes for on each iteration and returns `true` if any of the elements passes the condition passes or `false` if none of the elements passes condition.

Here is an example:

```js
let nums = [1, 2, 3, 4, 5];
let odd_nums = nums.some((num) => num % 2 !== 0);
console.log(odd_nums);
// => true
```

<!-- This will fail -->

```js
let nums = [1, 2, 3, 4, 5];
let num_greater_than_5 = nums.some((num) => num > 5);
console.log(num_greater_than_5);
// => false
```

## Array.prototype.sort()

The method destructively sorts the order of array elements it is invoked on **_in place_**. The method will sort the elements in ascending order by default.

Here is an example:

```js
let nums = [2, 1, 4, 3];
let sortd_nums = nums.sort();

console.log(sortd_nums);
// =>   [ 1, 2, 3, 4]
```

## Array.prototype.splice()

The method destructively modifies the contents of an array it is called on. The method either removes, adds and or modifies elements of an array **_in place_**.

Here is an example:

```js
let nums = [1, 2, 3, 4];

// insert 0 at the start of the array i.e index 0
// splice(position_to_insert, num_of_element_to_remove, element_to_insert)
let modified_nums = nums.splice(0, 0, 0);

console.log(modified_nums);
// =>   [] the array is empty since we did not delete any elements
console.log(nums);
// => [0, 1, 2, 3, 4]
```

## Array.prototype.toLocaleString()

This method returns a string form of the elements of the array it has been called on. The elements, in this case, are converted to their String representations and separated by a locale-specific delimiter String like a comma.

The method takes two optional arguments: `locales` as the first argument and `options` as the second argument. The method returns a string representation of the array element[s].

The default delimiter depends on the host's current locale as opposed to the `locales` parameter.

Here is an example without `locales` and `options`:

```js
let nums = [50, 75, 80, 450];

let nums_to_string = nums.toLocaleString();

console.log(nums_to_string);

// => "50,75,80,450"
```

Here's an example with `locales` and `options`:

```js
let prices = [50, 75, 80, 450];

let currencies = prices.toLocaleString("en", {
  style: "currency",
  currency: "USD",
});

console.log(currencies);

// => $50.00, $75.00, $80.00, $450.00
```

## Array.prototype.toString()

This method returns a string form of the elements of the array it has been called on. This method internally calls and overrides the `join()` method of `Object`s.

Here is an example:

```js
let nums = [50, 75, 80, 450];

let nums_to_string = nums.toString();

console.log(nums_to_string);

// => "50,75,80,450"
```

## Array.prototype.unshift()

This method add one or more elements at the start of an array-like object. The method takes at least one argument and returns the new length of the modified array.

Here is an example:

```js
let nums = [1, 2, 3, 4];

let modified_nums = nums.unshift(-1, 0);

console.log(modified_nums);

// => [-1, 0, 1, 2, 3, 4]
```

## Array.prototype.values()

This method is similar to `Array.prototype.keys`, except that instead of returning the indices, it returns an array iterator containing the -values of each element of the array.

Here is an example:

```js
let nums = [1, 2, 3, 4];

let num_values = nums.values();
for (const key of num_values) {
  console.log(value);
}
// => 1
// => 2
// => 3
// => 4
```

## Key Takeaways

In this article, we have discussed array methods in JavaScript. The article has covered most of the methods giving an example on how you can use each in your code.

However, the article may not be completely comprehensive. For further readings, refer to the following resources.

## References

[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
[W3S](https://www.w3schools.com/js/js_array_methods.asp)
