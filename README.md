# sql-collection

## What is Relational Database?
Relational database means the data is stored as well as retrieved in the form of relations (tables). 

Table 1 shows the relational database with only one relation called STUDENT which stores ROLL_NO, NAME, ADDRESS, PHONE and AGE of students.
STUDENT

| ROLL_NO | NAME   | ADDRESS | PHONE      | AGE |
|---------|--------|---------|------------|-----|
| 1       | RAM    | DELHI   | 9455123451 | 18  |
| 2       | RAMESH | GURGAON | 9652431543 | 18  |
| 3       | SUJIT  | ROHTAK  | 9156253131 | 20  |
| 4       | SURESH | DELHI   | 9156768971 | 18  |

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

### DML (Data Manipulation Language)
DML statements are used for managing data with in schema objects.
DML are of two types –
* Procedural DMLs : require a user to specify what data are needed and how to get those data.
Declerative DMLs (also referred as Non-procedural DMLs) : require a user to specify what data are needed without specifying how to get those data.
* Declarative DMLs are usually easier to learn and use than procedural DMLs. However, since a user does not have to specify how to get the data, the database system has to figure out an efficient means of accessing data.

### TCL (Transaction Control Language) 
Transaction Control Language commands are used to manage transactions in the database. These are used to manage the changes made by DML-statements. It also allows statements to be grouped together into logical transactions.
Following commands are used to control transactions. It is important to note that these statements cannot be used while creating tables and are only used with the DML Commands such as – INSERT, UPDATE and DELETE.
`````` sql
COMMIT: Commit command is used to permanently save any transaction
            into the database.
ROLLBACK: This command restores the database to last committed state.
            It is also used with savepoint command to jump to a savepoint
            in a transaction.
SAVEPOINT: Savepoint command is used to temporarily save a transaction so
            that you can rollback to that point whenever necessary.
``````

1. SET TRANSACTION: Places a name on a transaction.
Syntax:
`SET TRANSACTION [ READ WRITE | READ ONLY ];`
2. COMMIT: If everything is in order with all statements within a single transaction, all changes are recorded together in the database is called committed. The COMMIT command saves all the transactions to the database since the last COMMIT or ROLLBACK command.
Syntax:
`COMMIT;`
3. ROLLBACK: If any error occurs with any of the SQL grouped statements, all changes need to be aborted. The process of reversing changes is called rollback. This command can only be used to undo transactions since the last COMMIT or ROLLBACK command was issued.
Syntax:
`ROLLBACK;`
Example:
`````` sql
DELETE FROM Student WHERE AGE = 20;
ROLLBACK;
``````
or 
`````` sql
DELETE FROM Student WHERE AGE = 20;
COMMIT;
ROLLBACK;
``````
4. SAVEPOINT: creates points within the groups of transactions in which to ROLLBACK.
A SAVEPOINT is a point in a transaction in which you can roll the transaction back to a certain point without rolling back the entire transaction.
This command is used only in the creation of SAVEPOINT among all the transactions.
In general ROLLBACK is used to undo a group of transactions.
`````` sql
SAVEPOINT SP1;
//Savepoint created.
DELETE FROM Student WHERE AGE = 20;
//deleted
SAVEPOINT SP2;
//Savepoint created.
ROLLBACK TO SP1;
//Rollback completed.
``````
5. RELEASE SAVEPOINT:- This command is used to remove a SAVEPOINT that you have created.
Once a SAVEPOINT has been released, you can no longer use the ROLLBACK command to undo transactions performed since the last SAVEPOINT.

#### 

### DCL (Data Control Language) 
A Data Control Language is a syntax similar to a computer programming language used to control access to data stored in a database (Authorization). In particular, it is a component of Structured Query Language (SQL).
`````` sql
GRANT: allow specified users to perform specified tasks.
REVOKE: cancel previously granted or denied permissions.
``````

### Views
Views in SQL are kind of virtual tables. A view also has rows and columns as they are in a real table in the database. We can create a view by selecting fields from one or more tables present in the database. A View can either have all the rows of a table or specific rows based on certain condition.
Syntax:
`````` sql
CREATE VIEW view_name AS
SELECT column1, column2.....
FROM table_name
WHERE condition;

view_name: Name for the View
table_name: Name of the table
condition: Condition to select rows
``````

Create view from multiple tables.
`````` sql
CREATE VIEW MarksView AS
SELECT StudentDetails.NAME, StudentDetails.ADDRESS, StudentMarks.MARKS
FROM StudentDetails, StudentMarks
WHERE StudentDetails.NAME = StudentMarks.NAME;
``````

We can delete or drop a View using the DROP statement.
`DROP VIEW MarksView;`

#### UPDATING VIEWS
There are certain conditions needed to be satisfied to update a view. If any one of these conditions is not met, then we will not be allowed to update the view.
1. The SELECT statement which is used to create the view should not include GROUP BY clause or ORDER BY clause.
2. The SELECT statement should not have the DISTINCT keyword.
3. The View should have all NOT NULL values.
4. The view should not be created using nested queries or complex queries.
5. The view should be created from a single table. If the view is created using multiple tables then we will not be allowed to update the view.

We can use the CREATE OR REPLACE VIEW statement to add or remove fields from a view.
Syntax:
`````` sql
CREATE OR REPLACE VIEW view_name AS
SELECT column1,coulmn2,..
FROM table_name
WHERE condition;
``````

For example, if we want to update the view MarksView and add the field AGE to this View from StudentMarks Table, we can do this as:
`````` sql
CREATE OR REPLACE VIEW MarksView AS
SELECT StudentDetails.NAME, StudentDetails.ADDRESS, StudentMarks.MARKS, StudentMarks.AGE
FROM StudentDetails, StudentMarks
WHERE StudentDetails.NAME = StudentMarks.NAME;
``````

Inserting a row in a view:
We can insert a row in a View in a same way as we do in a table. We can use the INSERT INTO statement of SQL to insert a row in a View.Syntax:
`````` sql
INSERT INTO view_name(column1, column2 , column3,..) 
VALUES(value1, value2, value3..);

view_name: Name of the View
``````
**Inserting into a view is actually inserting into the real table, while deleting a row from a view is actually deleting from the real table.

Deleting rows from a view is also as simple as deleting rows from a table. We can use the DELETE statement of SQL to delete rows from a view. Also deleting a row from a view first delete the row from the actual table and the change is then reflected in the view.Syntax:
`````` sql
DELETE FROM view_name
WHERE condition;

view_name:Name of view from where we want to delete rows
condition: Condition to select rows 
``````

The WITH CHECK OPTION clause in SQL is a very useful clause for views. It is applicable to a updatable view. If the view is not updatable, then there is no meaning of including this clause in the CREATE VIEW statement.

* The WITH CHECK OPTION clause is used to prevent the insertion of rows in the view where the condition in the WHERE clause in CREATE VIEW statement is not satisfied.
* If we have used the WITH CHECK OPTION clause in the CREATE VIEW statement, and if the UPDATE or INSERT clause does not satisfy the conditions then they will return an error.

Example:
In the below example we are creating a View SampleView from StudentDetails Table with WITH CHECK OPTION clause.
`````` sql
CREATE VIEW SampleView AS
SELECT S_ID, NAME
FROM  StudentDetails
WHERE NAME IS NOT NULL
WITH CHECK OPTION;
``````
In this View if we now try to insert a new row with null value in the NAME column then it will give an error because the view is created with the condition for NAME column as NOT NULL.
For example,though the View is updatable but then also the below query for this View is not valid:
`````` sql
INSERT INTO SampleView(S_ID)
VALUES(6);
``````

### Indexes
Index is a schema object. It is used by the server to **speed up** the retrieval of rows by using a pointer. It can reduce disk I/O(input/output) by using a rapid path access method to locate data quickly. An index helps to speed up **select** queries and **where** clauses, but it slows down data input, with the **update** and the **insert** statements. Indexes can be created or dropped with no effect on the data.

```` sql
CREATE [UNIQUE] [CLUSTERED| NONCLUSTERED] INDEX <index_name>
ON <table_name>(<column>[ASC|DESC] [, <column>[ASC|DESC]...])
````

````sql
CREATE UNIQUE INDEX table_index
ON TABLE column;
````

3 types of indexes:
* Clustered – reorders the table according to the physical storage order and searches for information with the use of key values
* Non-clustered – maintains the order of the table
* Unique – forbids fields to have duplicated values

Unique indexes are used for the maintenance of the integrity of the data present in the table as well as for the fast performance, it does not allow multiple values to enter into the table.

Moreover, a table can have multiple non-cluster indexes, but only 1 single clustered one.

When should indexes be created –
* A column contains a wide range of values
* A column does not contain a large number of null values
* One or more columns are frequently used together in a where clause or a join condition

When should indexes be avoided –
* The table is small
* The columns are not often used as a condition in the query
* The column is updated frequently

Removing an Index – To remove an index from the data dictionary by using the `DROP INDEX index_name` command.

