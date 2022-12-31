Ah, the good old days of transactions without ORMs in Ruby 3. Those were the days when we had to do everything manually, without the convenience of those fancy object-relational mapping libraries.

But fear not, my fellow Rubyists! Even without ORMs, we can still use transactions to ensure the integrity of our database.

First, let's define a transaction. A transaction is essentially a group of database operations that are treated as a single unit of work. If any of the operations fail, the entire transaction is rolled back and none of the changes are applied to the database. This is useful for ensuring that our data remains consistent, even if something goes wrong.

Now, let's dive into the code. First, we'll need to establish a connection to our database.

Copy code
require 'pg'

conn = PG.connect(dbname: 'mydatabase')
Next, we'll want to start our transaction. To do this, we'll use the begin method.

Copy code
conn.exec('BEGIN')
Now, we can perform our database operations as usual. Let's say we want to update a record in our database.

Copy code
conn.exec("UPDATE users SET name = 'John' WHERE id = 1")
If everything goes according to plan, we can commit the transaction and apply the changes to the database.

Copy code
conn.exec('COMMIT')
But what if something goes wrong? Let's say we have a typo in our SQL statement and the update fails. In this case, we can roll back the transaction to undo any changes.

Copy code
conn.exec('ROLLBACK')
And that's it! With just a few simple lines of code, we can use transactions to ensure the integrity of our database. Of course, this is a bit more tedious than using an ORM, but it's still a viable option if you don't want to rely on those pesky libraries.

So go forth, my fellow Rubyists, and fear not the power of transactions! And if you're feeling particularly adventurous, you can even try doing this without a library at all. Good luck!




Tiberius Mairura
continue and give me examples in the same format
Now that we've covered the basics of transactions without ORMs in Ruby 3, let's take a look at some more advanced examples.

First, let's say we want to perform multiple database operations within a single transaction. To do this, we'll need to wrap our operations in a block of code and pass it to the transaction method.

Copy code
conn.transaction do
  conn.exec("UPDATE users SET name = 'John' WHERE id = 1")
  conn.exec("INSERT INTO users (name) VALUES ('Jane')")
end
If any of the operations within the block fail, the entire transaction will be rolled back and none of the changes will be applied to the database.

But what if we want to do some processing outside of the transaction block, and then commit the transaction if the processing is successful? In this case, we'll need to use the savepoint method to create a temporary checkpoint within the transaction.

Copy code
conn.exec('BEGIN')
conn.exec('SAVEPOINT my_savepoint')

# Do some processing here

if processing_successful?
  conn.exec('RELEASE SAVEPOINT my_savepoint')
  conn.exec('COMMIT')
else
  conn.exec('ROLLBACK TO SAVEPOINT my_savepoint')
end
This allows us to perform some processing outside of the transaction block, and then decide whether or not to commit the transaction based on the results of the processing.

Now, let's say we want to handle errors within the transaction block. To do this, we can use the rescue statement to catch any exceptions that may be thrown.

Copy code
begin
  conn.transaction do
    conn.exec("UPDATE users SET name = 'John' WHERE id = 1")
    raise 'Something went wrong!'
    conn.exec("INSERT INTO users (name) VALUES ('Jane')")
  end
rescue => e
  puts "An error occurred: #{e.message}"
  conn.exec('ROLLBACK')
end
In this example, the transaction will be rolled back if an exception is raised within the block. This allows us to handle errors and ensure that our database remains consistent.

So there you have it, a few more examples of how to use transactions without ORMs in Ruby 3. As you can see, it's not too difficult to implement transactions manually, and it can be a useful tool for ensuring the integrity of your database. Happy coding!
