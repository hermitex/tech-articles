So you want to know about duck typing in Ruby, huh? Well buckle up, because this is gonna be a wild ride!

First of all, what is duck typing? It's essentially a way of checking if an object can perform a certain action, rather than checking its type. In other words, if it looks like a duck, swims like a duck, and quacks like a duck, then it must be a duck.

Now let's see this in action with some code snippets. Let's say we have a class called Duck that has a method called quack.

class Duck
def quack
puts "Quack quack!"
end
end

duck = Duck.new
duck.quack # Outputs "Quack quack!"

Now let's say we have another class called Goose that also has a method called quack.

class Goose
def quack
puts "Honk honk!"
end
end

goose = Goose.new
goose.quack # Outputs "Honk honk!"

Now let's say we want to create a function that will take in any object and make it quack. We can do this using duck typing.

def make_it_quack(obj)
obj.quack
end

make_it_quack(duck) # Outputs "Quack quack!"
make_it_quack(goose) # Outputs "Honk honk!"

See how we didn't have to check the type of the object? We just assumed that if it has a quack method, it will be able to quack.

But wait, there's more! What if we have an object that doesn't have a quack method?

class Pig
def oink
puts "Oink oink!"
end
end

pig = Pig.new
make_it_quack(pig) # This will raise an error because the Pig class doesn't have a quack method

Oops, we forgot to add a check for this case. No problem, we can just use the respond_to? method to check if the object has a quack method before trying to call it.

def make_it_quack(obj)
if obj.respond_to?(:quack)
obj.quack
else
puts "Sorry, this object can't quack."
end
end

make_it_quack(pig) # Outputs "Sorry, this object can't quack."

And that's pretty much it for duck typing in Ruby! Just remember to always check if an object can perform a certain action before trying to call it, and you'll be quacking like a pro in no time.
