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
`Select employeeID from employee. INTERSECT Select EmployeeID from WorkShift` 