Topics in working with databases in ruby 3 without ORMS

Connecting to a database: In order to work with a database in Ruby, you first need to establish a connection to it. This can be done using various libraries or gems, such as MySQL2 or PG.

Executing SQL queries: Once you have a connection to your database, you can execute SQL queries to perform various operations such as inserting, updating, or deleting data. You can do this using methods like execute or query.

Working with result sets: When you execute a SELECT query, you'll often get back a result set containing multiple rows of data. You can then loop through the result set and process the data as needed.

Transactions: Transactions allow you to group multiple SQL statements into a single unit of work. This can be useful for ensuring data consistency and atomicity in your database operations.

Prepared statements: Prepared statements allow you to pre-compile a SQL statement and then execute it multiple times with different parameter values. This can improve performance and security by preventing SQL injection attacks.

Stored procedures: Stored procedures are pre-defined blocks of SQL code that can be called and executed by your application. They can be useful for encapsulating complex logic or for improving performance by reducing the number of round trips to the database.

Indexes: Indexes can help improve the performance of your database queries by allowing the database to quickly locate specific rows of data. You can create indexes on specific columns in your tables to speed up queries that filter or sort by those columns.

Normalization: Normalization is the process of organizing your data in a way that minimizes redundancy and dependency. By following certain rules for organizing your data, you can improve the performance and scalability of your database.

Data modeling: Data modeling involves designing your database schema to represent the relationships between different types of data. This can involve creating tables, columns, and relationships to model your data in a way that is efficient and easy to work with.
