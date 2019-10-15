# sql-collection

## What is Relational Database?
Relational database means the data is stored as well as retrieved in the form of relations (tables). 

Table 1 shows the relational database with only one relation called STUDENT which stores ROLL_NO, NAME, ADDRESS, PHONE and AGE of students.
STUDENT
![TABLE 1](student.png)

These are some important terminologies that are used in terms of relation.

* Attribute: Attributes are the properties that define a relation. e.g.; ROLL_NO, NAME etc.

* Tuple: Each row in the relation is known as tuple. The above relation contains 4 tuples, one of which is shown as:

1	RAM	DELHI	9455123451	18
* Degree: The number of attributes in the relation is known as degree of the relation. The STUDENT relation defined above has degree 5.

* Cardinality: The number of tuples in a relation is known as cardinality. The STUDENT relation defined above has cardinality 4.

* Column: Column represents the set of values for a particular attribute. The column ROLL_NO is extracted from relation STUDENT.

## Structured Query Language (SQL)
Structured Query Language is a standard Database language which is used to create, maintain and retrieve the relational database. Following are some interesting facts about SQL.
* SQL is case insensitive. But it is a recommended practice to use keywords (like SELECT, UPDATE, CREATE, etc) in capital letters and use user defined things (liked table name, column name, etc) in small letters.

* We can write comments in SQL using “–” (double hyphen) at the beginning of any line.

* SQL is the programming language for relational databases (explained below) like MySQL, Oracle, Sybase, SQL Server, Postgre, etc. Other non-relational databases (also called NoSQL) databases like MongoDB, DynamoDB, etc do not use SQL

* Although there is an ISO standard for SQL, most of the implementations slightly vary in syntax. So we may encounter queries that work in SQL Server but do not work in MySQL.

### SQL Categories
* Data Definition Language: It is used to define the structure of the database. e.g; CREATE TABLE, ADD COLUMN, DROP COLUMN and so on.

* Data Manipulation Language: It is used to manipulate data in the relations. e.g.; INSERT, DELETE, UPDATE and so on.

* Data Query Language: It is used to extract the data from the relations. e.g.; SELECT

* Transaction Control Language: used to manage transactions in the database. 

* Data Control Language: used to control access to data stored in a database (Authorization).

![SQL Commands](https://media.geeksforgeeks.org/wp-content/uploads/sql-commands.jpg)


