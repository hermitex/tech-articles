# Control Flow and Loops in Ruby

Control Flow and Loops in Ruby are used to execute a set of instructions multiple times until a certain condition is met. This allows us to automate repetitive tasks and make our code more efficient.

Control Flow is the order in which instructions are executed in a program. In Ruby, control flow is handled by using conditional statements such as if, else, and case.

If Statements:
If statements are used to execute a set of instructions if a certain condition is true. For example, the following code will print "Hello World" if the variable x is equal to 5:

```ruby
x = 5
if x == 5
  puts "Hello World"
end
```

Else Statements:
Else statements are used to execute a set of instructions if a certain condition is false. For example, the following code will print "Goodbye World" if the variable x is not equal to 5:

```ruby
x = 5
if x == 5
  puts "Hello World"
else
  puts "Goodbye World"
end
```

Case Statements:
Case statements are used to execute a set of instructions based on a certain value. For example, the following code will print "Hello World" if the variable x is equal to 5, and "Goodbye World" if the variable x is not equal to 5:

```ruby
x = 5
case x
when 5
  puts "Hello World"
else
  puts "Goodbye World"
end
```

Loops are used to execute a set of instructions multiple times until a certain condition is met. In Ruby, loops are handled by using the while, for, and each statements.

While Loops:
While loops are used to execute a set of instructions while a certain condition is true. For example, the following code will print the numbers 1 to 10:

```ruby
i = 1
while i <= 10
  puts i
  i += 1
end
```

For Loops:
For loops are used to execute a set of instructions for a certain number of times. For example, the following code will print the numbers 1 to 10:

```ruby
for i in 1..10
  puts i
end
```

Each Loops:
Each loops are used to execute a set of instructions for each element in an array. For example, the following code will print each element in the array:

```ruby
array = [1,2,3,4,5]
array.each do |element|
  puts element
end
```

Control Flow and Loops are essential concepts in Ruby programming. They allow us to automate repetitive tasks and make our code more efficient.

Relevant Links:
<https://www.tutorialspoint.com/ruby/ruby_loops.htm>
<https://www.tutorialspoint.com/ruby/ruby_control_statements.htm>
