# Working with Hashes in Ruby

Hashes in Ruby are a type of collection that stores key-value pairs. They are similar to arrays, but instead of using an integer index to access the elements, they use a key. This makes them very useful for storing data that needs to be associated with a specific label.

A hash is created using the Hash.new method, which takes an optional default value. This value will be returned if a key is accessed that does not exist in the hash.

## Example

```ruby
my_hash = Hash.new(0)
my_hash["a"] = 1
my_hash["b"] = 2

puts my_hash["c"] # => 0 (default value)
```

Hashes also have a number of useful methods for manipulating the data they contain. Here are some of the most commonly used methods:

### store: Stores a key-value pair in the hash

```ruby
my_hash.store("c", 3)
```

### fetch: Retrieves the value associated with a given key

```ruby
my_hash.fetch("c") # => 3
```

### keys: Returns an array of all the keys in the hash

```ruby
my_hash.keys # => ["a", "b", "c"]
```

### values: Returns an array of all the values in the hash

```ruby
my_hash.values # => [1, 2, 3]
```

### each: Iterates over each key-value pair in the hash

```ruby
my_hash.each { |key, value| puts "#{key}: #{value}" }
# => a: 1
#    b: 2
#    c: 3
```

### merge: Merges two hashes together, overwriting any duplicate keys

```ruby
other_hash = { "d" => 4, "e" => 5 }
my_hash.merge(other_hash) # => {"a"=>1, "b"=>2, "c"=>3, "d"=>4, "e"=>5}
```

### delete: Deletes a key-value pair from the hash

```ruby
my_hash.delete("c") # => 3 (the deleted value)
```

For more information on hashes in Ruby, see the official documentation: <https://ruby-doc.org/core-2.7.1/Hash.html>
