# MySql Interview Questions


What is difference between mysql,mysqli and pdo ?
```
MySQL is the old database driver, and MySQLi is the Improved driver.
The "i" stands for "improved" so it is MySQL improved.
MySQLi can be done procedural and object-oriented whereas MySQL can only be used procedurally.
Mysqli also supports prepared statements which protect from SQL Injection.
PDO (PHP Data Objects) is a general database abstraction layer with support for MySQL among many other databases.
```

what is mysql storage engines ?
```
A storage engine is a software module that a database management system uses to create, read, update data from a database.
There are two types of storage engines in MySQL: transactional and non-transactional. 
For MySQL 5.5 and later, the default storage engine is InnoDB.
The default engine is InnoDB
```
	
What is the difference between SQL and Mysql?
```
SQL(Structured Query Language) is a programming language created for managing data held in a Relational Database Management System.
Mysql is an open source, relational database management System.
```

difference between InnoDB and MyISAM
```
*	InnoDB has row-level locking, MyISAM can only do full table-level locking.
*	InnoDB has better crash recovery.
*	MyISAM has FULLTEXT search indexes, InnoDB did not until MySQL 5.6 (Feb 2013).
*	InnoDB implements transactions, foreign keys and relationship constraints, MyISAM does not.
```

What is the InnoDB?
```
*	InnoDB is a storage engine for the database management system MySQL. MySQL 5.5 and later use it by default. 
	It provides the standard ACID-compliant transaction features, along with foreign key support (Declarative 
	Referential Integrity).
```
	
What is acid in database?
```
*	In computer science, ACID (Atomicity, Consistency, Isolation, Durability) is a set of properties of 
	database transactions intended to guarantee validity even in the event of errors, power failures, etc.
```
	
What is SQL Server?
```
*	SQL Server is   one of the Database Management Systems (DBMS) and is designed by Microsoft.
*	SQL Server is free and anyone can download and use it.
*	The default port for MySQL Server is 3306.
```	

```
=>	DDL(Data Definition Language) dealing with database schemas as well as the description of how data resides in 
	the database. An example is CREATE TABLE command.
=>	DML denotes Data Manipulation Language such as SELECT, INSERT etc.
=>	DCL stands for Data Control Language and includes commands like GRANT, REVOKE etc.
```


Is there an object oriented version of MySQL library functions?
```
*	MySQLi is the object oriented version of MySQL and it interfaces in PHP.
```

Stored Procedure
```
*	Stored Procedure in SQL Server can be defined as the set of logical group of SQL statements.
*	A stored procedure is a set of SQL statements that can be stored in the server.
*	main benefit of using a stored procedure is that it increases the performance of the database because it reduces network traffic.
*	With a stored procedure, multiple calls can be melded into one.
*	Stored procedure is used to save time to write code again and again by storing the same in database and also 
	get the required output by passing parameters.
```
	
What do you mean by % and _ in the LIKE statement?
```
% corresponds to 0 or more characters. But _ is exactly one character in the LIKE statement.
```
In which language MySQL is written?
```
MySQL is written in C and C++ and its SQL parser is written in yacc.
```

What Is Caching?
```
Caching is the term for storing reusable responses in order to make subsequent requests faster. 
```

Caching Benefits
```
*	Decreased network costs
*	Improved responsiveness
*	Increased performance on the same hardware
*	Availability of content during network interruptions
```

What Can be Cached?
```
*	Logos and brand images
*	Non-rotating images in general (navigation icons, for example)
*	Style sheets
*	General Javascript files
*	Downloadable Content
*	Media Files
```

Locations Where Web Content Is Cached
```
Content can be cached at many different points throughout the delivery chain:
	1) Browser cache
	2) Intermediary caching proxies
	3) Reverse Cache
```
	
Levels of memory
```
	1) Level 1 or Register 
	2) Level 2 or Cache memory
	3) Level 3 or Main Memory
	4) Level 4 or Secondary Memory
```


object oriented
```
<?php
$servername = "localhost";
$username = "root";
$password = "";
$conn = new mysqli($servername, $username, $password);
if ($conn->connect_error) {
	die("Connection failed: " . $conn->connect_error);
}
echo "Connected successfully";
?>
```

PDO connection
```
<?php
$servername = "localhost";
$username = "root";
$password = "";
	try {
	$conn = new PDO("mysql:host=$servername;dbname=laxman_db", $username, $password);
	$conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
	echo "Connected successfully"; 
	}
	catch(PDOException $e)
	{
		echo "Connection failed: " . $e->getMessage();
	}
?>
```

procedural connection
```
<?php
$servername = "localhost";
$username = "root";
$password = "";
$conn = mysqli_connect($servername, $username, $password);
if (!$conn) {
	die("Connection failed: " . mysqli_connect_error());
}
echo "Connected successfully";
?>
```