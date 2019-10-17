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
* CHECK - Verifies that all values in a field satisfy a condition.
* DEFAULT - Automatically assigns a default value if no value has been specified for the field.
* UNIQUE - Ensures unique values to be inserted into the field.
* INDEX - Indexes a field providing faster retrieval of records.
* PRIMARY KEY - Uniquely identifies each record in a table.
* FOREIGN KEY - Ensures referential integrity for a record in another table.
