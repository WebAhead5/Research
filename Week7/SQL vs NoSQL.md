
# SQL vs NoSQL databases



:::success
Data is facts that can be transmitted or processed.
:::

:::info
Databases are systematic collection of data that makes it easier to manage that data.
:::

So in order to use and manage the databases we need a tool that help us storing, accessing and manipulating the data.

#### There are two ways of managing the data:

1. Relational Database - stores information in tables and every informational theme is stored in its own table.
So we are breaking the data into pieces, so using specific information from more than one table, needs to be ***joined***.
SQL (Structured Query Language) is an example of relational databases management.

2. Non-Relational Databases - the size and volume of data required developing a new solution that would help decreasing the response time.
MongoDB is an example of Non-relational database managment.


## The differences between SQL and NoSQL databases

![SQL vs NoSQL](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20191104165821/SQL-Vs-NoSQL1.png  "SQL vs NoSQL")

|   |  SQL |  NOSQL |
|---|---|---|
| Type  |  Relational Databases  |  NonRelational Databases |
| Language  |  sql and strict shema |   dynamic options without schema |
| Scalability  | vertically scalable  | horizontally scalable  |
| Structure   |  table-based | either key-value pairs, document-based, 		graph databases or wide-column stores  |
| Property followed  |  ACID properties (Atomicity, Consistency, Isolation and Durability) | CAP theorem (Consistency, Availability and Partition tolerance) |
|Support| vendors| rely on community support|

[Source](https://www.geeksforgeeks.org/difference-between-sql-and-nosql/) 




## Pros of SQL database

**<span style='color:green'> - Structured Data </span>**

SQL will be very useful when we have lot of data that’s needs to be structured in a very specific way, with different sets of data that relate to each other.

**<span style='color:green'> - ACID compliance </span>**

ACID stands for “ atomic, consistent, isolated and durable” where the idea is that either all changes you make to a database at one time happens together, or not at all.

**<span style='color:green'> - Joins </span>**

Often times we’ll need to retrieve multiple sets of data held in different tables. This is easily accomplished by ‘joining’ two or more tables together, and grabbing all of the information we need at once where in NoSQL, we'll need to retrieve multiple sets of data and make multiple queries to our database.


## Pros of NoSQL database


**<span style='color:green'> - Flexible & Schema-free </span>**

Flexibility to structure data without needing to abide by the row/column format.


![](https://www.guru99.com/images/1/101818_0537_NoSQLTutori3.png)

**<span style='color:green'> - Fast </span>**

By comparison NoSQL databases to SQL , they are much faster when we’re querying them.However, there’s no way to ‘join’ different sets of data as in SQL,so this functionality may worth the lose of speed.

**<span style='color:green'> - Ease of Use </span>**

Everything is represented as an object,making them very easy to reason about since we already know how objects work.


## Examples of the data structure of SQL!

in SQL databases first you declare a table schema which is constructed of
 - the schema field names 
 - the schema field types
example:
![](https://i.imgur.com/CSBNdXF.png)
------------------------

Combining schema and data provides us with structured data that we can then interact with in various ways. (example)
![](https://i.imgur.com/iPJAEEx.png)

------------------------

in a database you can have multiple tables (example)
![example of tables](https://i.imgur.com/BNXdK3Q.png)

------------------------


these tables can hold relationships between one another,
this is achieved by refrencing a unique identifier (an id or something else) of one table in another. examples

<img src="https://i.imgur.com/E5yPRH4.png" height="400px">

![](https://i.imgur.com/yuWAfcE.png)


![](https://i.imgur.com/tR1oVau.png)

## Examples of the data structure of NoSQL 

there are multiple different structures of storing data in NoSQL, to name a few:
- document based structure
- column based structure
- Graph based structure
- key - value pair based structure

each has their unique attributes and limitations


![](https://i.imgur.com/eT7M3qj.jpg)
![](https://i.imgur.com/q7HNSRw.jpg)
![](https://i.imgur.com/wJbYrPP.png)

## Examples of queries for SQL
    - SELECT * FROM Customers;
    
    - INSERT INTO table_name VALUES (value1, value2, value3, ...);
    
    - UPDATE Customers 
		SET ContactName = 'Alfred Schmidt', City= 'Frankfurt' 
		WHERE CustomerID = 1;
		
	- DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';
	
	- SELECT MIN(Price) AS SmallestPrice FROM Products;
	
	- SELECT * FROM Customers WHERE CustomerName LIKE 'a%';
	
	- SELECT Orders.OrderID, Customers.CustomerName
		FROM Orders
		INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID;



## Examples of queries for NoSQL databases (MongoDB as example)

    - db.inventory.find( {} ) // As {SELECT * FROM inventory} 
    
    - db.inventory.find( { status: "D" } )  // As { SELECT * FROM inventory WHERE status = "D"}
    
    - db.inventory.find( { status: "A", qty: { $lt: 30 } } ) // As SELECT * FROM inventory WHERE status = "A" AND qty < 30




## Resources/ More reading
- [(video) SQL vs NoSQL or MySQL vs MongoDB](https://www.youtube.com/watch?v=ZS_kXvOeQ5Y)
- [SQL relationships](https://launchschool.com/books/sql/read/table_relationships)
- [The differences between SQL and NoSQL databases](https://www.geeksforgeeks.org/difference-between-sql-and-nosql/) 









