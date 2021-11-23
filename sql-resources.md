# Sql interview questions

## I. Basic Knowledges

### What is Database

- Database is an organized collection of data, stored, and retrieved digitally from a remote or local computer system

- Databases can be vast and complex, an such databases are developed using fixed design and modeling approaches.

### What is SQL

- SQL stands for Structured Query Language.
  
- It is the standard language for relational database management systems. It is especially useful in handling organized data comprised of entities (variables) and relations between different entities of the data.

### What are Tables and Fields?

- Table is an organized collection of data stored in the form of rows and columns

- Columns can be categorized as vertical and rows as horizontal. The columns in the table are called fields while the rows can be referred to as records.

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

### What is a JOIN. List its different types.

The SQL join clause is used to combine records (rows) from two or more tables in a SQL database based on a related columns between the them.
**INNER JOIN** Retrieves records that have matching values in both tables involved in the join
**LEFT JOIN** Retrieves all the records/rows from the left and the matched record from the right table.
**RIGHT JOIN** Retrieves all the records from the right and matched record from the left table
**FULL JOIN** Retrieves all the records where there is a match in either the left or right table

### What is a self-join

A self-join is a cause of regular join where a table is joined to itself based on some relation between its own columns.

### What is an Index. Explain its different types

A database index is a data structure that provides a quick lookup of data in a column or columns of a table. It enhances the speed of operations accessing data from a database table at the cost of additional writes and memory to maintain the index data structure
**Unique and Non-Unique index**
Unique indexes are indexes that help maintain data integrity by ensuring that no two rows of data in the table have identical key values. Once a unique index has been defined for a table,
