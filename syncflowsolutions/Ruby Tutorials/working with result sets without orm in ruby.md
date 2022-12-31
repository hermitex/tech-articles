Working with result sets without ORMs in Ruby 3 can be a real pain in the butt. But hey, at least we get to feel like old-school programmers, right?

First things first, let's connect to our database. We'll use the MySQL2 gem for this:

Copy code
require 'mysql2'

# Connect to the database
client = Mysql2::Client.new(host: "localhost", username: "root", password: "root", database: "my_db")
Great, now we're connected. But wait, we don't have any ORM to do the heavy lifting for us. Time to roll up our sleeves and get our hands dirty.

Let's say we want to fetch all the users from the 'users' table in our database. We'll use the 'query' method to do this:

Copy code
# Fetch all users
users = client.query("SELECT * FROM users")
But hold on, this just returns a result set. We need to actually loop through the result set and extract the data we need.

Copy code
# Loop through result set and extract data
users.each do |row|
  puts row['id'] # Prints the user's id
  puts row['name'] # Prints the user's name
  puts row['email'] # Prints the user's email
end
See, that wasn't so bad. But wait, we're not done yet. We also need to consider things like prepared statements and binding variables to protect against SQL injection attacks.

Copy code
# Use prepared statement and binding variables to fetch user with specific id
stmt = client.prepare("SELECT * FROM users WHERE id = ?")
stmt.execute(5) # Fetch user with id 5
result = stmt.first
puts result['name'] # Prints the name of the user with id 5
Phew, that was a lot of work. But hey, at least we didn't have to deal with any of those fancy ORM things. Just plain old SQL and Ruby.

In conclusion, working with result sets without ORMs in Ruby 3 can be a bit of a hassle. But with a little bit of elbow grease, we can get the job done. Just don't forget to use prepared statements and binding variables to protect against SQL injection attacks. Happy coding!




Tiberius Mairura
continue in the same format but give more relevant examples
Alright, now that we've got the basics down, let's dive into some more advanced examples.

Say we want to perform a LEFT JOIN on two tables, 'users' and 'orders'. We can use the 'query' method again to accomplish this:

Copy code
# Perform LEFT JOIN on users and orders tables
results = client.query("SELECT * FROM users LEFT JOIN orders ON users.id = orders.user_id")
This will give us a result set containing all the rows from the 'users' table, even if there are no matching rows in the 'orders' table. Now we just need to loop through the result set and extract the data we need:

Copy code
# Loop through result set and extract data
results.each do |row|
  puts row['users.id'] # Prints the user's id
  puts row['users.name'] # Prints the user's name
  puts row['orders.id'] # Prints the order's id
  puts row['orders.product_name'] # Prints the order's product name
end
But what if we want to perform a more complex query, like a UNION? No problem, we can just use the 'query' method again:

Copy code
# Perform UNION on users and orders tables
results = client.query("(SELECT id, name, 'user' as type FROM users) UNION (SELECT id, product_name as name, 'order' as type FROM orders)")
This will give us a result set containing all the rows from both the 'users' and 'orders' tables, with a new 'type' column indicating whether the row is from the 'users' or 'orders' table.

As you can see, working with result sets without ORMs in Ruby 3 can be a bit of a challenge, but it's definitely doable. Just remember to use the 'query' method and loop through the result set to extract the data you need. Happy coding!
