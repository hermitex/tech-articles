# Working with Variables

Hey there! In Ruby, a variable is like a little suitcase for your data. You can stuff all kinds of stuff in there - numbers, strings, arrays, you name it! There are a few different types of variables to choose from, depending on what you're trying to do.

First up, we've got local variables. These are the most common type, and they're only accessible within the current method or block of code. They're kind of like the shy kids in school - they don't like to go out and socialize too much. To create a local variable, just give it a name and stuff it full of some data:

```ruby
x = 10
my_variable = "Hello, world!"
foo = [1, 2, 3]
```

Next up, we've got instance variables. These are like local variables, but they're only accessible within a particular instance of an object. They're denoted by an @ symbol, like @name or @age. To create an instance variable, just assign it a value:

```ruby
class Person
  def initialize(name, age)
    @name = name
    @age = age
  end

  def say_hello
    puts "Hi, my name is #{@name} and I am #{@age} years old."
  end
end

person = Person.new("Alice", 25)

person.say_hello # => "Hi, my name is Alice and I am 25 years old."
```

If you want to use a variable within a particular class, you can use a class variable. These start with a @@ symbol, like @@count or @@total. To create a class variable, just assign it a value:

```ruby
class Counter
  @@count = 0

  def self.increment
    @@count += 1
  end

  def self.count
    @@count
  end
end

Counter.increment
Counter.increment
puts Counter.count # => 2
```

Finally, we've got global variables. These are like the popular kids in school - they're available everywhere, and everyone knows their name. They start with a $ symbol, like $x or $foo. Just be careful with global variables, because they can get overwritten by other parts of your code, which can lead to some confusing bugs!

```ruby
$x = 10
def print_x
  puts $x
end

print_x # => 10
$x = 20
print_x # => 20
```

And that's it! I hope that helps, and if you have any more questions, just let me know. Happy coding!
