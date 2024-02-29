# Sql interview questions

## I. Basic Knowledges

### What is Database

- Database is an organized collection of data, stored, and retrieved digitally from a remote or local computer system

- Databases can be vast and complex, an such databases are developed using fixed design and modeling approaches.

### What is SQL

- SQL stands for Structured Query Language.
  
- It is the standard language for relational database management systems. It is especially useful in handling organized data comprised of entities (variables) and relations between different entities of the data.

## What are the different subsets of SQL?

- **Data Definition Language (DDL)**  It allows you to perform various operations on the database such as CREATE, ALTER, and DELETE objects. For example: create table, alter, and delete resources (table, table clones, views, user-defined functions,…)
- **Data Manipulation Language (DML)** It allows you to access and manipulate data. It helps you to insert, update, delete and retrieve data from the database.
- **Data Query Language (DQL)** to perform queries on the data in a database to retrieve the necessary information from it.
- **Data Control Language (DCL)** It allows you to control access to the database. like grant, revoke access permission
- **Transaction Control Language(TCL)** to control transactions in a database

### What are Tables and Fields?

- Table is an organized collection of data stored in the form of rows and columns

- Columns can be categorized as vertical and rows as horizontal. The columns in the table are called fields while the rows can be referred to as records.

### Whare are Tables and Views

- Table is an organized collection of data stored in the form of rows and colums

- View is a query in SWL that provides information about one or more tables, it is like looking into the database through a window. It is a virtual table perform when we run a query. It is not stored physically, it's is require some space in the memory whenever we runt its query. View only recreated.

### What are Constrants in SQL

Constraints are used to specify the rules concerning data in the table. It can be applied for single or multipe fields in an SQL table during the creation of the table or after creating using the **ALTER TABLE** command. The constraints are:

- **NOT NULL**: Restricts NULL value from being inserted into a column
  
- **CHECK**: Verifies that all values in the field satisfy a condition

- **DEFAULT**: Automatically assigns a default value if no value has been specified for the field

- **UNIQUE**: Ensures unique values to be inserted into the field

- **INDEX**: Indexes a field providing faster retrieval of records

- **PRIMARY KEY**: Uniquely identifies each record in a table

- **FOREIGN KEY**: Ensures referential integrity for a record into another table

### What is primary key?

The primary key constraint uniquely identifies each row in a table. It must contain UNIQUE values and has an implicit NOT NULL constraint.
A table in SQL is strickly restricted to have 1 and only one primary key, which is comprised of single or multiple fields (columns)

### What is UNIQUE constraint

A unique constraint ensures that all values in a column are different.
This provides uniqueness for the column(s) and help identify each row uniquely.

### What is foreign key

A foreign key comprises of a single or collection of fields in a table that essentially refers to the PRIMARY KEY in another table.
Foreign key constraint ensures referential integrit in the relation between two tables

## What is the difference between a primary key and unique key?

While both types of keys ensure unique values in a column of a table, the primary key identifies uniquely each record of the table, and the unique key prevents duplicates in that column

### What is an Alias?

A temporary name given to a table or a column in a table while executing a certain SQL query. Aliases are used to improve the code readability and make the code more compact.

### What is NULL value? how is it different from zero or a blank space?

A NULL value indicates the absence of data or the unknown status of a data ta item. Instead, zero is a valid numeric value, and an empty is a string of zero length

## What is the difference between local and global variables?

Local variable can be accessed only inside the function in which they were declared. Instead, global variables, being declared outside any function, are stored fixed memory structures and can be used throughout the entire program.

Some global variable: Identity, LanguageID, Error, RowCount

### What is a JOIN. List its different types

The SQL join clause is used to combine records (rows) from two or more tables in a SQL database based on a related columns between the them.
**INNER JOIN** Retrieves records that have matching values in both tables involved in the join
**LEFT JOIN** Retrieves all the records/rows from the left and the matched record from the right table.
**RIGHT JOIN** Retrieves all the records from the right and matched record from the left table
**FULL JOIN** Retrieves all the records where there is a match in either the left or right table

### What is a self-join

A self-join is a cause of regular join where a table is joined to itself based on some relation between its own columns.

### What is a Sub Query?

A query placed inside another query or an outer query. A subquery may occur in the clauses such as SELECT, FROM, WHERE, UPDATE,...

### How to create a temp table in SQL Server?

There are two ways. Create table hashtag(#) table name. the second is insert into hashtag table name.

## How to create empty tables with the same structure as another table?

Using the INTO operator to fetch the records of one table into a new table while setting a WHERE condition clause to false for all entries.

## List the different types of relationships in SQL?

**One-to-One** - a record in one table corresponds to the maximum of one record in the other (User and Password)

**One-to-Many and Many-to-One**: a record in one table is linked to several records in another (Class and Student)

**Many-to-Many**: is used when defining a relationship that requires several instances on each side (Book and Author)

### What is UNION, MINUS and INTERSECT commands?

**UNION** operator is used to combine the results of two tables while also removing duplicate entries

**MINUS** operator is used to return rows from the first from the first query but not from the second query

**INTERSECT** operator is used to combine the results of both queries into a single row.

***The condition***: the same amount of columns, data type, name, order

### What is an Index. Explain its different types

A database index is a data structure that provides a quick lookup of data in a column or columns of a table. It enhances the speed of operations accessing data from a database table at the cost of additional writes and memory to maintain the index data structure
**Unique and Non-Unique index**
Unique indexes are indexes that help maintain data integrity by ensuring that no two rows of data in the table have identical key values. Once a unique index has been defined for a table,

When used:

- A column contains a wide range of values
- A column does not contain a large number of null values
- One or more columns are frequently used together in a where clause or join a condition.

Should be avoid

- The table is small
- The columns are not often used as a condition in the query
- The column is updated frequently

Clustered Index

- Defines the order in which data is physically stored in a table. Table data can be sorted only way, therefore, there can be only one clustered index per table. (primary key).

Non-Clustered index

- Doesn’t sort the physical data inside the table. In fact, a non-clustered index is stored at one place and table data is stored in another place.
- The non-clustered contains column values on which the index created and the address of the record that value belongs to.
- The non-clustered index slower than Clustered index.

### What is CURSOR? How to use?

CURSOR is a temporary memory. It is allocated by Database Server at time of performing DML (Data Manipulation Language) operations on the table by the User.

- **Implicit Cursors**: are also known as Default Cursors of SQL server. These cursor are allocated by SQL SERVER when the user performs DML operations. For example: **%FOUND**: return true if insert, update or delete 1 or more rows or select into statement returns 1 or more rows. **%NOTFOUND**, **%ROUNDCOUNT**
- **Explicit Cursors**: are created by users whenever the user requires them.

To use default cursor. Declare a cursor with a select statement. open cursor and fetch the data (next, last, first,..) Close cursor and deallocated cursor to clear the resource connected.

Cursor is slow for some reasons: it mainly due to their row-by-row processing. it lock the current data process and it require more memory if result set is big.

To optimize: should avoid nested cursor, limit scope and duration, minimize fetches to reduce number of round-trips

### What is a function in SQL, and why use function?

A database object representing a set of SQL statement frequently used for a certain task. A function takes in some input parameters, performs calculations or other manipulations on them and returns the result.

- **Aggregate functions:** work on multiple, usually grouped record for the provided columns of a table, and return a single values (usually by group) (Sum, Min, Max…)
- **Scalar functions**: work on each individual value and return a single value (Len, Upper, Lower, Now, Round…)

### What is Store Procedure?

A store procedure is a set of Structured Query Language statements with an assigned name, which are stored in a relational management system as a group, so it can be reused and shared by multiple program.

Benefits:

- It is important layer of security between the user interface and the database. It support security through data access controls because end users many enter or change data, but do not write procedures.

- Store and Function can do the same task. But functions are defined to send their output to a query. Store procedures are design to return outputs to the application.

### What is trigger

It’s a special type of stored procedures that are defined to execute automatically in place or after data modification. It allow you to execute when insert, update or any other query is executed against a specific table.

- **After trigger** fire after the triggering action (INSERT, UPDATE, DELETE) has taken place

- **Instead of Trigger**: fired instead of the triggering action, allowing you to customize or override the default action

### TRUNCATE vs DELETE

**DELETE** is a Data Manipulation Language command used to delete one or more rows from a table based on the conditions specifies in the WHERE clause.

**TRUNCATE** is a Data Definition Language command used to delete all rows from a table.

**DELETE** works slower than **TRUNCATE**. Also, we can’t use truncate statement for a table containing a foreign key.

### DROP and TRUNCATE

**DROP** deletes a table from the database completely, including the table structure and all the associated constraints, relationships with other table and access privileges.

**TRUNCATE** deletes all rows from a table without effecting the table structure and constraint.

**DROP** works slower than **TRUNCATE**, both are Data Definition Language

### HAVING vs WHERE

HAVING works on aggregated data after they are grouped, while WHERE checks each row individually. If both statements are present in a query, they appear in the following order WHERE - GROUP BY - HAVING.

### What is normalization in SQL and why use it?

Normalization is a process of database design that includes organizing and restructuring data in a way to reduce data redundancy, dependency, duplication, an inconsistency. This leads to enhanced data integrity, more tables within the database, more efficient data access and security control, and greater query flexibility

Some advantages:

- Better Database organization
- More tables with smaller rows
- Efficient data access
- Greater flexibility for queries
- Quickly find the information
- Easier to implement security
- Allows easy modification
- Reduction of dependency, duplicate, and inconsistency.

### What is denormalization in SQL, and why use it.

It is a process opposite with normalization; it introduces data redundancy and combine data from multiple tables. Denormalization optimizes the performance of the database in situations when read operations are more important than write operation. It help avoid complex joins and reduces time of query running.

### What is SQL injection

SQL injection is a sort of flaw in website and web app code that allows attackers to take control of back-end processes and access, retrieve, and delete sensitive data stored in database.

Some example:

- Getting access to secret data in order to change SQL query
- UNION attacks are designed to steal data from several database table
- Examine the database to get information about the database version and structure

### Turning SQL

**Optimize Query**

- Use Indexes, make sure columns used in WHERE clauses, JOIN conditions and ORDER BY clauses are indexed.
- (*) avoid SELECT. Select what you need, not all columns
- Use Joins wisely: You join based on what you need, avoid unnecessary join that fetch more data than required
- Limit the result set: buy using LIMIT or TOP.

**Optimize Database Design**

- Normalization: Ensure the database properly normalized to reduce redundancy and improve data integrity
- Denormalization: in some cases, de-normalizing certain tables can improve query performance for read heavy operation.

**Index Strategies** 

- Primary key: for all every tables

Query Optimization Tecchniques

- Avoid cursors.
- Use EXISTS and IN when checking for existence of row, it can be faster than join
- Subquery.
- Using STORE PROCEDURE
