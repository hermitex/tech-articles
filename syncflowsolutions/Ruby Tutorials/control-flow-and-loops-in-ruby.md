# Control Flow and Loops in Ruby

Control Flow and Loops in ruby are like the wild, unpredictable ride at your local amusement park. You never quite know what's going to happen next, but that's what makes it so exciting! (Well, at least for us code geeks.)

First up, let's talk about control flow. This refers to the way in which your code is executed, and Ruby gives us a few different options for controlling the flow of our program.

One of the most basic control flow tools is the if/else statement. This allows us to specify a condition that, if true, will execute a certain block of code. If the condition is false, we can specify an alternate block of code to execute instead. Here's an example:

```ruby
if 2 + 2 == 4
  puts "Math still works!"
else
  puts "Uh oh, something's gone wrong with the universe."
end
```

As you can see, the if statement is followed by a condition (in this case, whether 2 + 2 equals 4). If the condition is true, the code inside the if block will execute. If it's false, the code inside the else block will execute instead.

We can also use an unless statement, which is basically the opposite of an if statement. It will execute a block of code only if the condition is false. Here's an example:

```ruby
unless 2 + 2 == 5
  puts "Whew, that was a close one!"
else
  puts "Uh oh, something's not right here."
end
```

Now let's move on to loops. Loops are great for when you want to repeat a block of code over and over again, either a specific number of times or until a certain condition is met.

One type of loop is the while loop. This will keep executing a block of code as long as the specified condition is true. Here's an example:

```ruby
i = 0
while i < 10
  puts "We're on loop number #{i}"
  i += 1
end
```

In this case, the loop will continue to run until the variable "i" reaches 10. Each time the loop runs, it will print out the current value of "i" and then increment it by 1.

Another type of loop is the until loop, which is similar to a while loop but executes the block of code only until the specified condition becomes true. Here's an example:

```ruby
i = 0
until i == 10
  puts "We're on loop number #{i}"
  i += 1
end
```

This loop will do the same thing as the while loop above, but it will run until the condition "i == 10" becomes true rather than continuing to run as long as it remains true.

Finally, we have the for loop, which is great for when you want to loop over a specific range of numbers. Here's an example:

```ruby
for i in 0..9
  puts "We're on loop number #{i}"
end
```

This loop will run 10 times, with "i" starting at 0 and incrementing by 1 each time.

So there you have it – a quick rundown of control flow and loops in Ruby. Just remember to hold on tight and enjoy the ride!
