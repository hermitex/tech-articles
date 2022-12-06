# Working with Variables

Variables are an essential part of any programming language, and Ruby is no exception. Variables are used to store data that can be used throughout a program. In Ruby, variables are declared using the assignment operator (=).

For example, if we wanted to create a variable called "name" and assign it the value "John", we would write:

```ruby
name = "John"
```

This statement creates a variable called "name" and assigns it the value of "John". We can then use this variable throughout our program. For example, if we wanted to print out the value of the variable, we could write:

```ruby
puts name
```

This would print out "John".

Variables in Ruby can also be used to store different types of data. For example, if we wanted to store a number in a variable, we could write:

```ruby
 number = 5
 ```

This statement creates a variable called "number" and assigns it the value of 5. We can then use this variable throughout our program. For example, if we wanted to add two numbers together, we could write:

```ruby
sum = number + 10
```

This statement creates a new variable called "sum" and assigns it the value of 15 (5 + 10).

Variables in Ruby can also be used to store objects. For example, if we wanted to create an array of strings, we could write:

```ruby
names = ["John", "Jane", "Joe"]
```

This statement creates a variable called "names" and assigns it the value of an array containing the strings "John", "Jane", and "Joe". We can then use this variable throughout our program. For example, if we wanted to print out the first element of the array, we could write:

```ruby
puts names[0]
```

This would print out "John".

Variables in Ruby can also be used to store the result of a method call. For example, if we wanted to get the length of a string, we could write:

```ruby
length = "John".length
```

This statement creates a variable called "length" and assigns it the value of 4 (the length of the string "John"). We can then use this variable throughout our program. For example, if we wanted to print out the length of the string, we could write:

```ruby
puts length
```

This would print out 4.

Variables in Ruby can also be used to store the result of a block. For example, if we wanted to get the sum of all the elements in an array, we could write:

```ruby
sum = [1, 2, 3].inject(0) { |total, n| total + n }
```

This statement creates a variable called "sum" and assigns it the value of 6 (the sum of all the elements in the array). We can then use this variable throughout our program. For example, if we wanted to print out the sum of the elements in the array, we could write:

```ruby
puts sum
```

This would print out 6.

Variables in Ruby can also be used to store the result of a conditional statement. For example, if we wanted to check if a number is greater than 5, we could write:

```ruby
result = (number > 5) ? "Yes" : "No"
```

This statement creates a variable called "result" and assigns it the value of "Yes" if the number is greater than 5, or "No" if the number is not greater than 5. We can then use this variable throughout our program. For example, if we wanted to print out the result of the conditional statement, we could write:

```ruby
puts result
```

This would print out either "Yes" or "No", depending on the value of the number.

In summary, variables in Ruby are an essential part of any program. They can be used to store different types of data, such as numbers, strings, objects, and the result of a method call or block. They can also be used to store the result of a conditional statement. By using variables, we can make our programs more efficient and easier to read.

Relevant Links:

<https://www.tutorialspoint.com/ruby/ruby_variables.htm>
<https://www.rubyguides.com/2018/10/ruby-variables/>
<https://www.techotopia.com/index.php/Ruby_Variables>
