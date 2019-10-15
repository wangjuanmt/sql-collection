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

### DQL (Data Query Language)

So first we will consider the Data Query Language. A generic query to retrieve from a relational database is:

1.SELECT [DISTINCT] Attribute_List FROM R1,R2….RM
2.[WHERE condition]
3.[GROUP BY (Attributes)[HAVING condition]]
4.[ORDER BY(Attributes)[DESC]];
Part of the query represented by statement 1 is compulsory if you want to retrieve from a relational database. The statements written inside [] are optional. We will look at the possible query combination on relation shown in Table 1.

#### AGGRATION FUNCTIONS
Aggregation functions are used to perform mathematical operations on data values of a relation. Some of the common aggregation functions used in SQL are:
* COUNT: Count function is used to count the number of rows in a relation. 
* SUM: SUM function is used to add the values of an attribute in a relation.
* GROUP BY: Group by is used to group the tuples of a relation based on an attribute or group of attribute. It is always combined with aggregation function which is computed on group. 
* AVG
* MAX
* MIN

### DDL (Data Definition Language) 
Integrity constraints used in DDL:
* Domain Constraints : A domain of possible values must be associated with every attribute (for example, integer types, character types, date/time types). Declaring an attribute to be of a particular domain acts as the constraints on the values that it can take.
* Referential Integrity : There are cases where we wish to ensure that a value appears in one relation for a given set of attributes also appear in a certain set of attributes in another relation i.e. Referential Integrity. For example, the department listed for each course must be one that actually exists.
* Assertions : An assertion is any condition that the database must always satisfy. Domain constraints and Integrity constraints are special form of assertions.
* Authorization : We may want to differentiate among the users as far as the type of access they are permitted on various data values in database. These differentiation are expressed in terms of Authorization. The most common being :
read authorization – which allows reading but not modification of data ;
insert authorization – which allow insertion of new data but not modification of existing data
update authorization – which allows modification, but not deletion.
