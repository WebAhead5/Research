# Database setup and maintenance
## What is a build script and why do you need one?


A build script is an <b>.sql</b> programme you can run to automatically build:
 - Your database;
 - Your tables;
 - Fill your tables with data;
 - and even run extra functions like set templates and DB properties.

Running scripts to create these things is best practice as it allows you to keep a record of the scripts run, allows to to re-run the same scripts on testing/production versions of your project, and provide you with a basis for debugging and source control in the event of any errors. In some cases you will be dealing with alot of tables/data when creating your databases, so using a script rather than the terminal makes this process much easier and faster.

<img src='https://i.imgur.com/x0Rkqtx.png'>


### Create Database

``CREATE DATABASE databasename`` is the standard command for creating a database

#### Here is complete Syntax of futher options in PostgreSQL

CREATE DATABASE db_name
OWNER =  role_name
TEMPLATE = template			
ENCODING = encoding			
LC_COLLATE = collate			
LC_CTYPE = ctype
TABLESPACE = tablespace_name
CONNECTION LIMIT = max_concurrent_connection

### Option	Description
- db_name:	Use this option to specify the name of the new database that you want to create. Although, you need to make sure that the database must be unique because If you attempt to create a new database with the same name as an existing database, PostgreSQL will display an error.
- role_name:	Use this parameter to define the the role name for the user who will own the new database. Default is postgres
- Template	You can specify database template name from which you want to creates the new database.
- Encoding: This parameter allows specifying character set encoding for the new database. Default is UTF8
- Collate: The collation parameter specifies the sort order of strings which affect the result of the ORDER BY clause while using a SELECT statement.
- Ctype	: It specifies the character classification for the new database. It affects the categorization, e.g., digit, lower and upper.
- tablespace_name :	Using this option you can specify the tablespace name for the new database. The default is the template database's tablespace.
- max_concurrent_connection	: Use this option to specify the maximum concurrent connections to the new database. The default is -1, i.e., unlimited.

[Link to Database Creation Documentation](https://www.postgresql.org/docs/12/sql-createdatabase.html)


### Create Table

``CREATE TABLE tablename (column name, data type, constraint)`` is the standard command for creating a table. 

Here you can set the colum names (ID, Name, Location etc.), data types (VARCHAR, Interger, Serial, text etc) and constraints (NOT NULL, UNIQUE, Primary Key, Default etc.) - <i>see [Documentation](https://www.postgresql.org/docs/12/sql-createtable.html) for full list of options.</i>

#### Here are a few addtional useful properties you can set:

- <b>TEMP or TEMPORARY</b>:	This parameter creats a temporary table. Temporary tables are deleted at the end of a session, or at after the current transaction.
- <b>If not exists:</b>If a table already exisits with a same name, a warning is shown instead of an error
- <b>Of_type_name:</b>	A table that takes structure from the specified composite type.

[Link to Table Creation Documentation](https://www.postgresql.org/docs/12/sql-createtable.html)

###  Insert Values

Once the Database and the Table are created, you can then insert data in the the usual way:

``INSERT INTO table (name, location)`` 
``VALUES  
('name1', 'location1 ),
('name2', 'location2),
('name3', 'location3);``

[Link to Table Creation Documentation](https://www.postgresql.org/docs/9.1/sql-insert.html)


### Scripts (Transactions)

There are lots of commands that can be used to run PSQL scripts, here are a few key ones:

Running scripts in PSQL can be done in the following way:

``BEGIN`` start a transaction/code block

[Begin Documentation Link](https://www.postgresql.org/docs/9.1/sql-begin.html)

``COMMIT`` commits the current transaction. All changes made by the transaction become visible to others and are guaranteed to be durable if a crash occurs.

[Commit Documentation Link](https://www.postgresql.org/docs/9.1/sql-begin.html)


``CHECKPOINT``  force a transaction log checkpoint.  A checkpoint is a point in the transaction log sequence at which all data files have been updated to reflect the information in the log. 

[Checkpoint Documentation Link](https://www.postgresql.org/docs/9.1/sql-checkpoint.html)


``SAVEPOINT``  A savepoint is a special mark inside a transaction that allows all commands that are executed after it was established to be rolled back, restoring the transaction state to what it was at the time of the savepoint.

[Savepoint Documentation Link](https://www.postgresql.org/docs/9.1/sql-savepoint.html)


``ROLLBACK TO SAVEPOINT``  Roll back all commands that were executed after the savepoint was established.  

[Rollback Documentation Link](https://www.postgresql.org/docs/9.1/sql-rollback-to.html)



#### Running Scripts

Scripts can be run externally as an .sql file, or inside PSQL using ``\i /filedir/filename``





## What is the difference between a development, testing and production database?


- <b>Development Database</b>: for intial testing and trialing of ideas and scripts.
- <b>Testing Database:</b> for testing and QA once project is through the development phase, but not yet ready to go live.
- <b>Production Database:</b> for day to day use with real end user data.

Each environment should have a separate database. Script all of the database objects (tables, views, procedures, etc) and store the scripts in source control. The scripts are applied first to the development database, then promoted to test, then production. By applying the same scripts to each database, they should all be the same in the end.

If you have data that needs to be loaded (code tables, lookup values, etc), script that data load as part of the database creation process. By scripting everything and keeping it in source control, a database structure can be recreated at any time for any given build level.





## Creating a production database on Heroku



#### <span style='color:blue'>Create a new app</span>
<img src='https://i.imgur.com/iYPvbKw.png'>

#### <span style='color:blue'>Click on the app that you just created and then go to Configure Add-ons</span>

<img src='https://i.imgur.com/vK1jn5e.png'>

#### <span style='color:blue'>Search for postgres add-on and add it</span>

<img src='https://i.imgur.com/pWUOXP9.png'>

#### <span style='color:blue'>then you can go to the settings and add your Database env variable</span>

<img src='https://i.imgur.com/2Zai8G3.png'>

#### <span style='color:blue'>You can then use the link in the VALUE with the command psql or pgcli [postgress://blablabla:333333]</span>


Useful link:  [Deploying Database to Heroku](https://devcenter.heroku.com/articles/heroku-postgresql#connecting-in-node-js)




## Example build script:


Example build script from Week 7 day 1 PG workshop (data.sql):

![script](https://i.ibb.co/vmrR6JR/buildscript.png)






## Useful Links
- [Deploying to Heroku](https://devcenter.heroku.com/articles/heroku-postgresql#connecting-in-node-js)
- [PostgreSQL documentation](https://www.postgresql.org/docs/)
- [Mockaroo - for generating mock build scripts & data](https://www.mockaroo.com/)
