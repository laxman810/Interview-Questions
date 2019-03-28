# PHP Interview Questions



What does the initials of PHP stand for?
```
PHP means PHP: Hypertext Preprocessor.
```

What is the difference between == and === operator in PHP ?
```
The difference between the two is that '==' should be used to check if the values of the two operands are equal or not. 
On the other hand, '===' checks the values as well as the type of operands.
```
	
What is the use of Constant Function?
```
A constant function is used to return the constant value.
```

What are the different types of errors in PHP?
```
Parse Error – Commonly caused due to syntax mistakes in codes.
Fatal Error – These are basically runtime errors which are caused when you try to access what cannot be done.
Warning Error – This error occurs when you try to include a file that is not present.
Notice Error – This error occurs when you try to utilize a variable that has not been declared.
```

In PHP, objects are they passed by value or by reference?
```
In PHP, objects passed by value.
```

What is the main difference between PHP 4 and PHP 5?
```
PHP 5 presents many additional OOP (Object Oriented Programming) features.
```

Is multiple inheritance supported in PHP?
```
PHP supports only single inheritance; it means that a class can be extended from only one single class using the keyword 'extended'.
```

What is the meaning of a final class and a final method?
```
'final' is introduced in PHP5. Final class means that this class cannot be extended and a final method cannot be overridden.
```

What is needed to be able to use image function?
```
GD library is needed to execute image functions.
```

What’s the difference between unset() and unlink()
```
The unlink() function is dedicated for file system handling. It simply deletes the file given as entry.
The unset() function is dedicated for variable management. It will make a variable undefined.
```

How do I escape data before storing it in the database?
```
The addslashes function enables us to escape data before storage into the database.
```

How can you pass a variable by reference?
```
To be able to pass a variable by reference, we use an ampersand in front of it, as follows $var1 = &$var2
```

What are Traits?
```
Traits are a mechanism for code reuse in single inheritance languages such as PHP.
A Trait is intended to reduce some limitations of single inheritance by enabling a developer to reuse sets of methods 
freely in several independent classes living in different class hierarchies. A Trait cannot be instantiated on its own.
```	

session_destroy in php
```
session_destroy() destroys all of the data associated with the current session.
It does not unset any of the global variables associated with the session, or unset the session cookie.
To use the session variables again, session_start() has to be called.
session_destroy();
```
	
How can I prevent SQL injection in PHP?
```
*  Use prepared statements and parameterized queries.
*  Using PDO (for any supported database driver):
*  Using MySQLi (for MySQL):
```

delete cookies in php
```
unset($_COOKIE[$cookie_name]);
// empty value and expiration one hour before	
$res = setcookie($cookie_name, '', time() - 3600);
```
	
What are the __construct() and __destruct() methods in a PHP class?
```
__construct() is the most common magic method in PHP, because it is used to set up a class when it is initialized. 
The opposite of the __construct() method is the __destruct() method. This method is called when there are no more 
references to an object that you created or when you force its deletion.
```

What’s the difference between the include() and require() functions?
```
if include() is not able to find a specified file on location at that time it will throw a warning 
however, it will not stop script execution. For the same scenerio require() will throw 
fatal error and it will stop the script execution.
```

Type of error in php
```
- E_ERROR: A fatal error that causes script termination
- E_WARNING: Run-time warning that does not cause script termination
- E_PARSE: Compile time parse error.
- E_NOTICE: Run time notice caused due to error in code
- E_CORE_ERROR: Fatal errors that occur during PHP's initial startup (installation)
- E_CORE_WARNING: Warnings that occur during PHP's initial startup
- E_COMPILE_ERROR: Fatal compile-time errors indication problem with script.
- E_USER_ERROR: User-generated error message.
- E_USER_WARNING: User-generated warning message.
- E_USER_NOTICE: User-generated notice message.
- E_STRICT: Run-time notices.
- E_RECOVERABLE_ERROR: Catchable fatal error indicating a dangerous error
- E_ALL: Catches all errors and warnings
```

Multiple Inheritance in PHP
```
*	Many of the object oriented programming languages, like C#, Java and PHP do not support multiple inheritance. 
	To allow this feature, you can use interfaces in PHP or you can use "Traits" in PHP instead of classes for implementing 
	multiple inheritance in PHP. Therefore we are concerned about what "Traits" are. So the answer is that "A Trait is 
	similar to an abstract class, that cannot be instantiated on its own and a Trait is intended to reduce some limitations 
	of single inheritance by enabling a developer to reuse sets of methods freely in several independent classes living 
	in various class hierarchies". 
```

What is the difference between GET and POST?
```
GET displays the submitted data as part of the URL, during POST this information is not shown as it’s encoded in the request.
GET can handle a maximum of 2048 characters, POST has no such restrictions.
GET allows only ASCII data, POST has no restrictions, binary data are also allowed.
Normally GET is used to retrieve data while POST to insert and update.
```

Can the value of a constant change during the script’s execution?
```
No, the value of a constant cannot be changed once it’s declared during the PHP execution.
```

Can you extend a Final defined class?
```
No, you cannot extend a Final defined class. 
A Final class or method declaration prevents child class or method overriding.
```

What are the __construct() and __destruct() methods in a PHP class?
```
All objects in PHP have Constructor and Destructor methods built-in. 
The Constructor method is called immediately after a new instance of the class is being created, 
and it’s used to initialize class properties. The Destructor method takes no parameters.
```

What is MIME?
```
MIME (Multi-Purpose Internet Mail Extensions) is an extension of the original Internet e-mail protocol 
that lets people use the protocol to exchange different kinds of data files on the Internet: 
audio, video, images, application programs, and other kinds, as well as the ASCII text handled in the original protocol.
```

Explain the difference between $message and $$message?
```
* $message is used to store variable data. $$message can be used to store variable of a variable. 
Data stored in $message is fixed while data stored in $$message can be changed dynamically.
Example
$Message = "YOU";
$you= "Me";
echo $message //Output:- you
echo $$message //output :-Me
```

What are the reasons for selecting lamp instead of combination of other software programs, servers and operating systems?
```
All of those are open source resource. Security of linux is very very more than windows. 
Apache is a better server that IIS both in functionality and security. Mysql is world most 
popular open source database. PHP is more faster that asp or any other scripting language.
```

What is Zend Engine?
```
* Zend Engine is used internally by PHP as a compiler and runtime engine. 
	PHP Scripts are loaded into memory and compiled into Zend opcodes.
* These opcodes are executed and the HTML generated is sent to the client.
```

What are some new features introduced in PHP7?
```
* Zend Engine 3 performance improvements and 64-bit integer support on Windows
* uniform variable syntax AST-based compilation process
* added Closure::call()
* bitwise shift consistency across platforms
* (null coalesce) operator
* Unicode codepoint escape syntax
* return type declarations
* scalar type (integer, float, string and boolean) declarations.
```

What are the major difference between PHP 5 and PHP 7?
```
* PHP 7 was released in December 2015.
* PHP 7 enables you to use anonymous classes
* If anonymous classes are used well, they can speed up coding as well execution time. 
  Anonymous classes are excellent when a class is used only once during execution and 
  in cases when a class doesn’t need to be documented.
* The major difference between PHP5 and PHP7 is the performance
* Abstract Syntax Tree:which has made parsing easier and less error free.
* Closure::call() : – This is the new method added into PHP7. It allows variable binding at call time rather than per-binding.
* Spaceship Operator: New addition in PHP7, this operator can be used in sorting and combined comparisons. 
  It works like strcmp() and version_compare(). EX =>   return $a <=> $b;
```
	
In PHP 5, what is the difference between using self and $this?
```
* Use $this to refer to the current object. Use self to refer to the current class. 
In other words, use  $this->member for non-static members, use self::$member for static members.
```

How do I get PHP errors to display?
```
ini_set('display_errors', 1);
ini_set('display_startup_errors', 1);
error_reporting(E_ALL);
```

=> md5() vs. crypt() vs. sha1()?
```
sha1() is the only one to use.
```

How can we encrypt password using PHP?
```
crypt () function is used to create one way encryption.
```

How can we increase the execution time of a PHP script?
```
* Default time allowed for the PHP scripts to execute is 30 secs mentioned in the php.ini file.
* Using sleep() function in PHP script
* Using set_time_limit() function
* The default limit is 30 seconds. The time limit can be set to zero to impose no time limit to pause.
```

What is htaccess? Why do we use this and where?
```
* htaccess files are configuration files of Apache Server that provide a way to make 
  configuration changes on a per-directory basis. A file, containing one or more configuration directives, 
  is placed in a particular document directory, and the directives apply to that directory, and all subdirectories thereof.
*  These .htaccess files are used to change the functionality and features of Apache web server.
For instance, htaccess file is used for url rewrite.
–> It is used to make the site password protected.
–> .htaccess file can restrict some ip addresses so that on restricted ip addresses, the site will not open.
```

What are magic methods?
```
* Magic methods are member functions that are available to all the instance of class. 
	Magic methods always start with “__”. Eg. __construct.
* All magic methods need to be declared as public
* To use a method, it should be defined within the class or program scope
*Various Magic Methods used in PHP 5 are:
	__construct() __destruct() __set() __get() __call() __toString() 
	__sleep() __wakeup() __isset() __unset() __autoload() __clone().
```
	
What is meant by PEAR in PHP?
```
* PEAR is an acronym for “PHP Extension and Application Repository” The purpose of PEAR is to provide:
* A structured library of open-sourced code for PHP users
* A system for code distribution and package maintenance
* A standard style for writing code in PHP.
* PHP Foundation Classes (PFC)
* PHP Extension Community Library (PECL)
* It extends PHP and gives a higher level of programming for all web developers. 
```

What is Memcache?
```
* Memcache is a technology that caches objects in memory such that your web application can get to them really fast. 
	It is used by sites such as Digg.com, Facebook.com and NowPublic.com 
	and is widely recognized as an essential ingredient in scaling any LAMP.
```

PECL
```
=>	PECL is a repository for PHP Extensions, providing a directory of all known extensions and hosting facilities 
	for downloading and development of PHP extensions.
=>	The packaging and distribution system used by PECL is shared with its sister, PEAR.
```

Composer
```
=>	Composer is an application-level package manager for the PHP programming language that provides a 
	standard format for managing dependencies of PHP software and required libraries.
```

curl
```
Client URL Request Library
curl is a tool to transfer data from or to a server, using one of the supported protocols 
(DICT, FILE, FTP, FTPS, GOPHER, HTTP, HTTPS, IMAP, IMAPS, LDAP, LDAPS, POP3, POP3S, RTMP, 
RTSP, SCP, SFTP, SMB, SMBS, SMTP, SMTPS, TELNET and TFTP).
curl is powered by libcurl for all transfer-related features.
```

abstract class
```
An abstract class is a class that is only partially implemented by the programmer. 
It may contain one or more abstract methods. 
An abstract method is simply a function definition that serves to tell the programmer that the method 
must be implemented in a child class.
```
	
What is the content type header?
```
The Content-Type entity header is used to indicate the media type of the resource. 
In responses, a Content-Type header tells the client what the content type of the returned content actually is.
In requests, (such as POST or PUT ), the client tells the server what type of data is actually sent.
```

What is use of header() function in php?
```
1. Header is used to redirect from current page to another:
	header("Location: newpage.php");
2. Header is used to send Send a raw HTTP header
	header('Content-Type: application/pdf');
```

What is HTTP caching?
```
A web cache (or HTTP cache) is an information technology for the temporary storage (caching) of web documents, 
such as HTML pages and images, to reduce bandwidth usage, server load, and perceived lag.
```