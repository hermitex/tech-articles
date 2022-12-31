Ah yes, the age-old question of how to execute SQL queries without an ORM in Ruby 3. Why would anyone want to do such a thing, you may ask? Well, perhaps you're a masochist and enjoy the extra work. Or maybe you just really, really love SQL and can't bear to use an ORM to abstract it away. Whatever the reason, I'm here to guide you through the process of executing those pesky SQL queries without the use of an ORM.

First things first, let's start with the basics. In order to execute SQL queries without an ORM, you'll need a database connection. You can use the mysql2 gem to establish a connection to a MySQL database like so:

Copy code
require 'mysql2'

client = Mysql2::Client.new(host: "localhost", username: "your_username", password: "your_password", database: "your_database")
Now that you have a database connection, you can execute your SQL queries using the client.query method. For example, to select all rows from a table called "users", you can do the following:

Copy code
results = client.query("SELECT * FROM users")
But wait, there's more! What if you want to insert a new row into the "users" table? No problem, just use the client.query method again and pass in an INSERT INTO statement:

Copy code
client.query("INSERT INTO users (name, email) VALUES ('John', 'john@example.com')")
You can also use placeholders in your SQL queries to prevent injection attacks. Simply use the ? character as a placeholder and pass in the values as an array. For example:

Copy code
name = "John"
email = "john@example.com"
client.query("INSERT INTO users (name, email) VALUES (?, ?)", name, email)


Updating rows: To update a row in a table, you can use the UPDATE statement. For example, to update the name of a user with an id of 1:
Copy code
client.query("UPDATE users SET name = 'Jane' WHERE id = 1")
Deleting rows: To delete a row from a table, you can use the DELETE statement. For example, to delete the user with an id of 1:
Copy code
client.query("DELETE FROM users WHERE id = 1")
Creating tables: To create a new table in your database, you can use the CREATE TABLE statement. For example, to create a table called "posts" with a title and content column:
Copy code
client.query("CREATE TABLE posts (id INTEGER PRIMARY KEY AUTO_INCREMENT, title VARCHAR(255), content TEXT)")
Dropping tables: To delete a table from your database, you can use the DROP TABLE statement. For example, to delete the "posts" table:
Copy code
client.query("DROP TABLE posts")
As you can see, executing SQL queries without an ORM in Ruby 3 is quite simple. Just remember to use the client.query method and pass in your SQL statement as a string. Happy coding!

So there you have it! Executing SQL queries without an ORM in Ruby 3 is as easy as 1, 2, 3. Just remember to use placeholders to prevent injection attacks and you'll be good to go. Happy querying!
