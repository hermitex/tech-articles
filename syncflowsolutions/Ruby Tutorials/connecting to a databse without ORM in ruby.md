Well, if you're a masochist like me, you might just love working with databases without an ORM in Ruby 3. I mean, sure, ORMs like ActiveRecord make it easy to interact with databases and save us from writing SQL queries, but where's the fun in that?

Hey there fellow Ruby enthusiasts! Are you tired of using those pesky ORM's (Object-Relational Mapping) to connect to your databases? Well, have no fear because I'm here to show you how to connect to a database without ORMS in the latest and greatest version of Ruby - Ruby 3!

First things first, let's make sure we have the necessary gems installed. For this tutorial, we'll be using the mysql2 gem to connect to a MySQL database. So, in your Gemfile, make sure you have the following line:

gem 'mysql2'

Next, let's require the mysql2 gem in our Ruby file.

require 'mysql2'

Now we're ready to start connecting to our database! The first thing we need to do is create a client object to represent our connection to the database. To do this, we'll use the Mysql2::Client.new method and pass in a hash containing our connection details.

client = Mysql2::Client.new(
host: 'localhost',
username: 'your_username',
password: 'your_password',
database: 'your_database'
)

And just like that, we're connected to our database! But wait, we're not done yet. We still need to actually run some SQL queries on our database.

To run a SQL query, we'll use the client object's query method and pass in our SQL string. Let's say we want to select all the records from a table called 'users'. Here's how we would do it:

results = client.query("SELECT * FROM users")

Now, the results variable will contain an array of hashes, where each hash represents a row in the table. We can iterate over this array and access the values for each column using the column name as the key.

results.each do |row|
puts row['username']
end

And there you have it, folks! You've just learned how to connect to a database and run SQL queries without the use of ORMS in the latest version of Ruby. Now go forth and conquer those databases!
