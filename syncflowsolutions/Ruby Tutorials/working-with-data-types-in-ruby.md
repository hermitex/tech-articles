# Data Types in Ruby for Beginners

Hey there! So you want to learn about data types in Ruby? Great choice! Ruby is a dynamic language, which means that it can handle a variety of data types without you having to specify them upfront. Let's dive in and see what types of data we can play with in Ruby!

First up, we have the trusty ol' integers. These are your basic whole numbers, like 1, 2, 3, and so on. In Ruby, you don't have to worry about specifying whether you're using a regular integer or a long integer like in some other languages. Ruby can handle them all! Here's an example of some integers in action:

```ruby
puts 1 + 2 # prints 3
puts 50 - 25 # prints 25
puts 100 * 2 # prints 200
puts 10 / 5 # prints 2
```

Next up, we have floating point numbers, or "floats" for short. These are numbers with decimal points, like 3.14 or 0.5. Floats are great for when you need a little more precision in your calculations. Here's an example of some floats in action:

```ruby
puts 3.14 + 2.718 # prints 5.858
puts 10.0 / 3.0 # prints 3.3333333333333335
puts 5.5 * 2 # prints 11.0
```

In addition to numbers, Ruby also has a couple of different types of strings. A string is just a bunch of characters strung together, like "Hello, world!" or "I love Ruby!". You can use single quotes or double quotes to define a string, but there are some slight differences between the two. For example, if you want to include a single quote in a single-quoted string, you have to escape it like this: 'I'm a single-quoted string!'. On the other hand, if you use double quotes, you can just include the single quote without any issues: "I'm a double-quoted string!". Here's an example of some strings in action:

```ruby
puts "Hello, world!"
puts 'I love Ruby!'
puts "I'm a double-quoted string!"
puts 'I\'m a single-quoted string!'
```

We also have boolean values in Ruby, which can only be true or false. These are useful for when you want to check if something is true or not. For example, you might use a boolean value to check if a number is even or odd. Here's an example of some booleans in action:

```ruby
puts true
puts false
puts 1.even? # prints true
puts 2.even? # prints false
```

Next on is the Symbol. A symbol is kind of like a string, but it's stored in a more efficient way and can't be changed. Symbols are usually used as keys in hashes (more on that later). You can define a symbol by putting a colon in front of a word, like this: :symbol. Here's an example of some symbols in action:

```ruby
puts :symbol
puts :symbol.object_id # prints the object ID of the symbol
puts "string".object_id # prints the object ID of the string
```

Arrays: An array is a collection of values that are stored in a single variable. You can think of an array as a list of items. You can define an array by enclosing a list of values in square brackets, like this: [1, 2, 3, 4]. You can access individual values in an array using their index (the position of the value in the array), starting at 0 for the first value. Here's an example of an array in action:

```ruby
# Define an array of numbers
numbers = [1, 2, 3, 4]

# Access the first value
puts numbers[0] # prints 1

# Access the second value
puts numbers[1] # prints 2

# Modify the third value
numbers[2] = 10
puts numbers[2] # prints 10
```

Hashes: A hash is a collection of key-value pairs. You can think of a hash as a dictionary, where you can look up a value using its associated key. You can define a hash by enclosing a list of key-value pairs in curly braces, like this: {key1: value1, key2: value2}. You can access the value of a particular key using the square bracket notation, like this: hash[:key]. Here's an example of a hash in action:

```ruby
# Define a hash of names and ages
ages = {john: 25, sarah: 30, peter: 35}

# Access the age of John
puts ages[:john] # prints 25

# Modify the age of Sarah
ages[:sarah] = 28
puts ages[:sarah] # prints 28
```

Modules: A module is a way to group related methods, constants, and other Ruby code into a single unit. You can think of a module as a kind of "toolbox" that you can use to organize your code and make it easier to reuse. You can define a module by using the module keyword, like this:

```ruby
module MyModule
  # code goes here
end
You can then include the module in a class using the include keyword, like this:

Copy code
class MyClass
  include MyModule
  # code goes here
end
```

Classes: A class is a way to define a new custom data type in Ruby. You can think of a class as a blueprint for creating objects. An object is an instance of a class, and it can have its own set of attributes (variables) and methods (functions). You can define a class by using the class keyword, like this:

```ruby
class MyClass
  # code goes here
end
```

You can then create an object of the class by calling the new method, like this:

```ruby
my_object = MyClass.new
```

I hope this gives you a better idea of the other data types that are available in Ruby. As you can see, there are a few more advanced data types that you might encounter as you progress in your Ruby journey. Don't worry if these seem a bit confusing at first - just keep practicing and you'll get the hang of it in no time! So, these are the main data types in Ruby.
