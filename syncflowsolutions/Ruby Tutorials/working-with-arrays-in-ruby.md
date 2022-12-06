# Working with Arrays in Ruby

Arrays are a fundamental data structure in Ruby, and they are used to store collections of objects. An array is an ordered list of elements, and each element can be accessed by its index. Arrays are mutable, meaning that their elements can be changed or replaced.

## Creating an Array

In Ruby, there are several ways to create an array. The most common way is to use the Array class:

```ruby
my_array = Array.new
```

This creates an empty array. You can also create an array with elements by passing them as arguments to the Array class:

```ruby
my_array = Array.new(1, 2, 3)
```

This creates an array with the elements 1, 2, and 3. You can also use the array literal syntax to create an array:

```ruby
my_array = [1, 2, 3]
```

This creates an array with the same elements as the previous example.

## Accessing Elements

Once you have created an array, you can access its elements by using their index. The first element in an array has an index of 0, and the last element has an index of the array’s length minus one. For example, if you have an array with three elements, the last element has an index of 2.

```ruby
my_array = [1, 2, 3]
my_array[0] # => 1
my_array[1] # => 2
my_array[2] # => 3
```

You can also use negative indices to access elements from the end of the array. For example, if you have an array with three elements, the last element has an index of -1.

```ruby
 my_array = [1, 2, 3]
my_array[-1] # => 3
my_array[-2] # => 2
my_array[-3] # => 1
```

## Adding and Removing Elements

You can add elements to an array using the << operator or the push method. The << operator adds an element to the end of the array, while the push method adds an element to the beginning of the array.

```ruby
my_array = [1, 2, 3]
my_array << 4 # => [1, 2, 3, 4]
my_array.push(5) # => [5, 1, 2, 3, 4]
```

You can also remove elements from an array using the pop method or the delete_at method. The pop method removes the last element from the array, while the delete_at method removes an element at a specified index.

```ruby
my_array = [1, 2, 3]
my_array.pop # => 3
my_array # => [1, 2]
my_array.delete_at(0) # => 1
my_array # => [2]
```

## Array Methods

Ruby provides a number of methods for working with arrays. Here are some of the most commonly used methods:

• each: Iterates over each element in the array and passes it to a block.
• map: Iterates over each element in the array and passes it to a block, then returns an array with the results of the block.
• select: Iterates over each element in the array and passes it to a block, then returns an array with the elements for which the block returns true.
• sort: Sorts the elements in the array.
• reverse: Reverses the order of the elements in the array.
• uniq: Removes duplicate elements from the array.
• include?: Checks if the array includes a specified element.
• length: Returns the number of elements in the array.

## Example

Here is an example of using some of these methods to work with an array:

```ruby
my_array = [1, 2, 3, 4, 5]
```

## Iterate over each element and print it

```ruby
my_array.each { |x| puts x }
# => 1
# => 2
# => 3
# => 4
# => 5
```

## Map each element to its square and return a new array

```ruby
squares = my_array.map { |x| x * x }
# => [1, 4, 9, 16, 25]
```

## Select only even elements

```ruby
evens = my_array.select { |x| x.even? }
# => [2, 4]
```

## Sort the elements

```ruby
my_array.sort # => [1, 2, 3, 4, 5]
```

## Reverse the order of the elements

```ruby
my_array.reverse # => [5, 4, 3, 2, 1]
```

## Remove duplicate elements

```ruby
my_array.uniq # => [1, 2, 3, 4, 5]
```

## Check if the array includes a specified element

```ruby
my_array.include?(3) # => true
```

## Get the number of elements in the array

```ruby
my_array.length # => 5
```

Conclusion

Arrays are a fundamental data structure in Ruby, and they are used to store collections of objects. Arrays are mutable, meaning that their elements can be changed or replaced. Ruby provides a number of methods for working with arrays, such as each, map, select, sort, reverse, uniq, include?, and length.
