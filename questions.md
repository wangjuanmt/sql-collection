The following questions are from [advanced-sql-interview-questions](https://www.geeksforgeeks.org/advanced-sql-interview-questions/)
### Que-1: Explain the meaning of ‘index’.
Explanation:
Indexes help retrieve information from the database faster and with higher efficiency. In other words, it’s a method that enhances performance and there are 3 types of indexes:

1.Clustered – reorders the table and searches for information with the use of key values
2.Non-clustered – maintains the order of the table
3.Unique – forbids fields to have duplicated values

Moreover, a table can have multiple non-cluster indexes, but only 1 single clustered one.

### Que-2: You forgot your root password, what do you do ?
Explanation:
Start the database with the command of “skip-grants-table”.
After you set the new password, restart the database in normal mode and enter the new password.


### Que-3: Are NULL values equal to a zero ?
Explanation:
No, because a “zero” has a numerical manner and NULL represent the absence of a character. This happens when the character is unknown or unavailable. Additionally, NULL shouldn’t be confused with blank space because data record without any value assigned is not the same as a plain blank space, with no data records attached.


### Que-4: Data disk gets overloaded, what do you do ?
Explanation:
You should apply a soft link: these links create a location where you are able to store your .frm and .idb files. This will resolve the overload problem.


### Que-5: Explain what‘auto increment’ is?
Explanation:
This command allows you to generate a unique number when a new record is written to a table. When you want to the primary key field value to be generated automatically each time you insert a new record, this is when this function comes in handy.
Another thing worth noting is that the command can be used on various platforms. For SQL Servers the “auto increment” command is “identity”.


### Que-6: What are the most basic MySQL architecture components ?
Explanation:
There are three main components:
Query optimizer;
Connection manager;
Pluggable engine.


### Que-7: Using an existing table, make an empty one.
Explanation:
`Select * into employeecopy from employee where 1=2`


### Que-8: How would you check your current SQL version ?
Explanation:
You can get the most current SQL version by issuing this command:
SELECT VERSION()


### Que-9: Get alternative odd records from the table.
Explanation:
This can be achieved using the command:
`Select id from employee where mod(id, 2)=1`


### Que-10: What command would select a unique record from the table ?
Explanation:
The “distinct” command. Here’s an example:
`Select DISTINCT employeeID from Employee `


### Que-11: What are variables of SQL ?
Explanation:
In SQL, there are two different variables: 

Local – these variables can only exist in one single function
Global – are the opposite of local, which means they can be located throughout the entire program.


### Que-12: What is a ‘datawarehouse’ and what it does ?
Explanation:
A “datawarehouse” is a system used for data analysis and reporting. Basically, it’s a warehouse of data. Data in DWs can be stored from various areas and sources and thus makes them central repositories of integrated data that is ready for usage.

### Que-13: For what ‘recursive stored procedure’ is mainly used ?
Explanation:
A recursive stored procedure is a procedure that will make the code calls itself until specific boundary condition is reached. This is a productivity type of thing, that allows programmers to use the same code a number of times.


### Que-14: Retrieve the first 3 characters from a character string.
Explanation:
There are a few ways to do this. Nevertheless, the command presented below can be treated as a more popular and easier one:
`Select SUBSTRING(EmployeeSurname, 1, 3) as employeesurname from employee`


### Que-15: How would you retrieve common records from two tables ?
Explanation:
By performing the task below:
`Select employeeID from employee INTERSECT Select EmployeeID from WorkShift` 

The following questions are from [sql-interview-questions](https://www.interviewbit.com/sql-interview-questions/)

### 1. What is Database?
A database is an organized collection of data, stored and retrieved digitally from a remote or local computer system. Databases can be vast and complex, and such databases are developed using fixed design and modeling approaches.

### 2. What is DBMS?
DBMS stands for Database Management System. DBMS is a system software responsible for the creation, retrieval, updation and management of the database. It ensures that our data is consistent, organized and is easily accessible by serving as an interface between the database and its end users or application softwares.

### 3. What is RDBMS? How is it different from DBMS?
RDBMS stands for Relational Database Management System. The key difference here, compared to DBMS, is that RDBMS stores data in the form of a collection of tables and relations can be defined between the common fields of these tables. Most modern database management systems like MySQL, Microsoft SQL Server, Oracle, IBM DB2 and Amazon Redshift are based on RDBMS.

### 4. What is SQL?
SQL stands for Structured Query Language. It is the standard language for relational database management systems. It is especially useful in handling organized data comprised of entities (variables) and relations between different entities of the data.

### 5. What is the difference between SQL and MySQL?
SQL is a standard language for retrieving and manipulating structured databases. On the contrary, MySQL is a relational database management system, like SQL Server, Oracle or IBM DB2, that is used to manage SQL databases.

### 6. What are Tables and Fields?
A table is an organized collection of data stored in the form of rows and columns. Columns can be categorized as vertical and rows as horizontal. The columns in a table are called fields while the rows can be referred to as records.

### 7. What are Constraints in SQL?
Constraints are used to specify the rules concerning data in the table. It can be applied for single or multiple fields in an SQL table during creation of table or after creationg using the ALTER TABLE command. The constraints are:

* NOT NULL - Restricts NULL value from being inserted into a column.
* CHECK - Verifies that all values in a field satisfy a particular condition.
* DEFAULT - Automatically assigns a default value if no value has been specified for the field.
* UNIQUE - Ensures unique values to be inserted into the field (column).
* INDEX - Indexes a field providing faster retrieval of records.
* PRIMARY KEY - Is a field which can uniquely identify each row in a table. 
* FOREIGN KEY - Ensures referential integrity for a record in another table. A Foreign key is a field which can uniquely identify each row in another table.

We can specify constraints at the time of creating the table using CREATE TABLE statement. We can also specify the constraints after creating a table using ALTER TABLE statement.

```` sql
CREATE TABLE Orders
(
O_ID int NOT NULL,
ORDER_NO int NOT NULL,
C_ID int,
PRIMARY KEY (O_ID),
FOREIGN KEY (C_ID) REFERENCES Customers(C_ID)
)
````

```` sql
CREATE TABLE Student
(
ID int(6) NOT NULL UNIQUE,
NAME varchar(10) NOT NULL,
AGE int NOT NULL CHECK (AGE >= 18)  // CHECK
);
````

```` sql
CREATE TABLE Student
(
ID int(6) NOT NULL,
NAME varchar(10) NOT NULL,
AGE int DEFAULT 18  // DEFALUT
);
````

### 11. What is a Join? List its different types.
The SQL Join clause is used to combine records (rows) from two or more tables in a SQL database based on a related column between the two.
![different types of join](https://assets.interviewbit.com/assets/skill_interview_questions/sql/sql-join-types-8bc666e6be3a47e2fb8ef456f8c36ab473dce46d797d40b4bfbc3c60dcc2c6da.png.gz)

There are four different types of JOINs in SQL:

(INNER) JOIN: Retrieves records that have matching values in both tables involved in the join. This is the widely used join for queries.
```` sql
SELECT *
FROM Table_A
JOIN Table_B;

SELECT *
FROM Table_A
INNER JOIN Table_B;
````

LEFT (OUTER) JOIN: Retrieves all the records/rows from the left and the matched records/rows from the right table.
```` sql
SELECT *
FROM Table_A A
LEFT JOIN Table_B B
ON A.col = B.col;
````

RIGHT (OUTER) JOIN: Retrieves all the records/rows from the right and the matched records/rows from the left table.
```` sql
SELECT *
FROM Table_A A
RIGHT JOIN Table_B B
ON A.col = B.col;
````

FULL (OUTER) JOIN: Retrieves all the records where there is a match in either the left or right table.
```` sql
SELECT *
FROM Table_A A
FULL JOIN Table_B B
ON A.col = B.col;
````

### 12. What is a Self-Join?
A self JOIN is a case of regular join where a table is joined to itself based on some relation between its own column(s). Self-join uses the INNER JOIN or LEFT JOIN clause and a table alias is used to assign different names to the table within the query.
```` sql
SELECT A.emp_id AS "Emp_ID",A.emp_name AS "Employee",
B.emp_id AS "Sup_ID",B.emp_name AS "Supervisor"
FROM employee A, employee B
WHERE A.emp_sup = B.emp_id;
````

### 13. What is a Cross-Join?
Cross join can be defined as a cartesian product of the two tables included in the join. The table after join contains the same number of rows as in the cross-product of number of rows in the two tables. If a WHERE clause is used in cross join then the query will work like an INNER JOIN.
```` sql
SELECT stu.name, sub.subject 
FROM students AS stu
CROSS JOIN subjects AS sub;
````

![cross-join](https://assets.interviewbit.com/assets/skill_interview_questions/sql/sql-self-cross-join-ac01aba97313e5f8740292417b156d4cdd524a5c5ac4efc3acd77d38434af4b8.png.gz)


