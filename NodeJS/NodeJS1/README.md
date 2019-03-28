# NodeJS Interview Questions

What is Node.js?
```
=>	Node.js is a Server side scripting which is used to build scalable programs. 
	It is a web application framework built on Google Chrome?s JavaScript Engine. 
=> 	Node JS applications uses “Single Threaded Event Loop Model” architecture to handle multiple concurrent 
	clients.
=> 	There are many web application technologies like JSP, Spring MVC, ASP.NET, HTML, Ajax, jQuery etc. 
	But all these technologies follow “Multi-Threaded Request-Response” architecture to handle multiple 
	concurrent clients.
=> 	As HTTP is a Stateless Protocol, this Request/Response model is also Stateless Model. 
	So we can call this as Request/Response Stateless Model.
=> 	Node.js is a very powerful JavaScript based platform or framework which is built on Google Chrome's 
	JavaScript V8 Engine.
=> 	NodeJS is a runtime system, which is used for creating server-side applications.
=>	Node.js is a server-side JavaScript platform which is built on Google Chrome’s JavaScript V8 engine. 
=>	It is an open source and cross platform application to develop server side and networking applications.
```

V8 engine
```
V8 is Google’s open source high-performance JavaScript engine.
V8 engine written in C++ and used in Google Chrome.
V8 can run standalone, or can be embedded into any C++ application.
V8 Engine Translates JavaScript into Machine Code
```

Features of Node.js
```
• Fast in Code execution
• Highly scalable
• Event Driven and Asynchronous
• No Buffering
• Asynchronous and Event Driven
• Single Threaded but Highly Scalable
```
	
Where Not to Use Node.js?
```
It is not advisable to use Node.js for CPU intensive applications.
```

Where to Use Node.js?
```
• I/O bound Applications
• Data Streaming Applications
• Data Intensive Real-time Applications (DIRT)
• JSON APIs based Applications
• Single Page Applications
```

Why to use Node.js?
```
It is used to develop I/O intensive web applications like video streaming sites, single page applications 
and other web applications. Node.js is open source and used by thousands of developers around the world.
```

what is Microprocessors ?
```
Microprocessors are tiny machines that work with electrical signals and ultimately do the job. 
We give microprocessors the instructions. The instructions are in the language that microprocessors 
can interpret. Different microprocessors speak different languages. Some of the most common are 
IA-32, x86–64, MIPS, and ARM. These languages directly interact with the hardware so the code 
written in them is called machine code. Code that we write on our 
computers is converted or compiled into machine code.
```

Who developed Node.js?
```
Node.js was developed in 2009 by Ryan Dahl.
```

What is Package.json?
```
package.json is present in the root directory of any Node application/module and is used 
to define the properties of a package.
```
	
What is Callback?
```
=>  Callback is an asynchronous equivalent for a function. A callback function is called at the completion 
	of a given task. Node makes heavy use of callbacks. All APIs of Node are written is such a way that 
	they supports callbacks.For example, a function to read a file may start reading file and return 
	the control to execution environment immidiately so that next instruction can be executed. 
	Once file I/O is complete, it will call the callback function while passing the callback function, 
	the content of the file as parameter. So there is no blocking or wait for File I/O.This makes Node.js 
	highly scalable, as it can process high number of request without waiting for any function to return result.
=>  Callback is called once the asynchronous operation has been completed. 
	Node.js heavily uses callbacks and all API’s of Node.js are written to support callbacks.
```	
	
Explain REPL in Node.js?
```
	REPL stands for Read Eval Print Loop.
	The REPL stands for Read Eval Print Loop, which is a simple program that accepts the commands, 
evaluates the commands, and prints their results. It represents a computer environment like Unix/Linux 
shell or a window console in which we can enter the command and the system responds with output. 
REPL performs the following tasks:
=> Eval
=> Print
=> Loop
=> Read
```

Explain NPM in Node.js?
```
=> NPM stands for Node Package Manager (npm) and there are two functionalities which NPM takes care of mainly 
	and they are –
=> Online repositories for node.js modules or packages, which can be searched on search.nodejs.org
=> Dependency Management, Version Management and command line utility for installing Node.js packages.
=> npm is used for managing the Node.js Package.
=> npm makes it easy for JavaScript developers to share the code that they've created to solve particular problems, and for other developers to reuse that code in their own applications.
=> These bits of reusable code are called packages, or sometimes modules.
```

How Node.js can be made more scalable?
```
Node.js works good for I/O bound and not CPU bound work. 
```
	
Explain “Callback hell”?
```
“Callback hell” will be referred to heavily nested callbacks which has become unreadable or unwieldly.
```

What are “Streams” in Node.JS?
```
“Streams” are objects which will let you read the data from source and write data to 
destination as a continuous process.
```
	
Explain Child process module?
```
=> spawn  - child_process.spawn launches a new process with a given command.
=> exec  - child_process.exec method runs a command in a shell/console and buffers the output.
=> fork - The child_process.fork method is a special case of the spawn() to create child processes.
```

Node.js Console
```
=>	console.log('Hello Learner');   
=>	console.log('Hello %s', 'Learner');   
=>	console.error(new Error('Hell! This is a wrong error.'));  
=>	const name = 'Laxman';  
=>	console.warn(`Don't mess with me ${name}! Don't mess with me!`);
```

What is the difference between tilde(~) and caret(^)  in the package.json ?
```
=> In the simplest terms, the tilde matches the most recent minor version (the middle number). ~1.2.3 will 
	match all 1.2.x versions but will miss 1.3.0.
=> The caret, on the other hand, is more relaxed. It will update you to the most recent major version (the first number).
   ^1.2.3 will match any 1.x.x release including 1.3.0, but will hold off on 2.0.0.
```
   
What is the difference between Bower and npm?
```
=>  they can be used together in a single project.
=> 	The biggest difference is that npm does nested dependency tree (size heavy) while Bower requires a flat dependency tree.
=> 	A nested dependency tree means that your dependencies can have their own dependencies which can have their own, and so on. 
	This is really great on the server where you don't have to care much about space and latency.
=> 	It lets you not have to care about dependency conflicts as all your dependencies use e.g. their own version of Underscore. 
	This obviously doesn't work that well on the front-end. Imagine a site having to download three copies of jQuery.
=> 	The reason many projects use both is that they use Bower for front-end packages and npm for developer tools like 
	Yeoman, Grunt, Gulp, JSHint, CoffeeScript, etc.
=> It is much harder to avoid dependency conflicts without nesting dependencies. This is fundamental to the way
	that npm works, and has proven to be an extremely successful approach.
=> Bower is optimized for the front-end. Bower uses a flat dependency tree, requiring only one version for 
	each package, reducing page load to a minimum.
```

What is the difference between call and apply?
```
=> The difference is that apply lets you invoke the function with arguments as an array; 
	call requires the parameters be listed explicitly. A useful mnemonic is "A for array and C for comma."
=> theFunction.apply(valueForThis, arrayOfArgs)
=> theFunction.call(valueForThis, arg1, arg2, ...)
```

What's the difference between using “let” and “var” to declare a variable?
```
=> The difference is scoping. var is scoped to the nearest function block and let is scoped to the nearest enclosing block, 
	which can be smaller than a function block. Both are global if outside any block.
=> Also, variables declared with let are not accessible before they are declared in their enclosing block.
	As seen in the demo, this will throw a ReferenceError exception.
	let me = 'go';  // globally scoped
	var i = 'able'; // globally scoped
'use strict';
let me = 'foo';
let me = 'bar'; // SyntaxError: Identifier 'me' has already been declared
'use strict';
var me = 'foo';
var me = 'bar'; // No problem, `me` is replaced.
```

Difference between == and === in JavaScript 
```
=> JavaScript has both strict and type-converting equality comparison.
0 == false   // true
0 === false  // false, because they are of a different type
1 == "1"     // true, automatic type conversion for value only
1 === "1"    // false, because they are of a different type
null == undefined // true
null === undefined // false
'0' == false // true
'0' === false // false
```

what is cdn in jquery
```
A Content Delivery Network (CDN) is a system of computers that exist all over the world and cache files
for users to access. CDNs can greatly reduce the load time of a page by offering files at a higher 
bandwidth from a server that is physically closer to your visitor than your web server might be.
```

server-side cache
```
=> This is where server-side cache comes in handy. The goal of server side cache is responding to the same 
	content for the same request independently of the client’s request. 
	In our example above, the first request that reaches our server would still take 2 seconds to generate the HTML, 
	but the following requests would hit the cache instead and 
	the server would be able to send the response in a few milliseconds.
=> There are many ways of doing it, it could be done with NGINX or a CDN like CloudFlare
```

Node.js Streams
```
=>	Streams are the objects that facilitate you to read data from a source and write data to a destination. 
	There are four types of streams in Node.js:
=>	Readable: This stream is used for read operations.
=>	Writable: This stream is used for write operations.
=>	Duplex: This stream can be used for both read and write operations.
=>	Transform: It is type of duplex stream where the output is computed according to input.
=>	Each type of stream is an Event emitter instance and throws several events at different times. 
	Following are some commonly used events:
* Data:This event is fired when there is data available to read.
* End:This event is fired when there is no more data available to read.
* Error: This event is fired when there is any error receiving or writing data.
* Finish:This event is fired when all data has been flushed to underlying system.
```

Node.js Buffers
```
=>	Node.js provides Buffer class to store raw data similar to an array of integers but corresponds to a 
	raw memory allocation outside the V8 heap.
=>	Buffer class is used because pure JavaScript is not nice to binary data. So, when dealing with TCP 
	streams or the file system, it's necessary to handle octet streams.
=>	Buffer class is a global class. It can be accessed in application without importing buffer module.
=>	temporary storage spot for a chunk of data that is beign transferd from
	one place to another
=>  increase the performance of application
=>  transfer bit by bit data not whole large data
=>	no need to load whole big file in memory
=>  stream use to transfer data from point A to point B
```

Increase the Memory Limit for Your Process Node.Js
```
=>  The system process of Node.js starts your applications with a default memory limit. 
	If you’re going to run an application that saves a lot of data into variables and therefore memory,
	you may run into a Node.js process exit due to allocation issues.
=>	const v8 = require('v8');
=>	v8.getHeapStatistics()
=>	node --max-old-space-size=16000 server.js
```

How do I update Node.js and npm on Windows?
```
* all Programs search for Windows PowerShell
* right-click PowerShell and select 'Run as Administrator'.
* run below command
* Set-ExecutionPolicy Unrestricted -Scope CurrentUser -Force
* npm install -g npm-windows-upgrade
* npm-windows-upgrade
* update to the latest by running 
* npm-windows-upgrade -p -v latest
```

Nodejs export modules
```
=>	reusable code
=>	each file is treated as a separate module.
=>	module.exports or exports, will be exposed as a module
=>	module.exports = 'Hello world';
=>	exports = 'Hello world';
=>	exports.msg = 'Hello world';
=>	module.exports.msg = 'Hello world';
=>	Module Types:
		Core Modules
		Local Modules
		Third Party Modules(http, url,querystring,path, fs,util)
```

Nodejs Debugger
```
=>	use inspect argument
=>	$ node inspect myscript.js
=>	Inserting the statement debugger; into the source code of a script will enable a
	breakpoint at that position in the code:
	// myscript.js
	global.x = 5;
	setTimeout(() => {
	  debugger;
	  console.log('world');
	}, 1000);
	console.log('hello');
=>	watch('my_expression').
=>	unwatch('my_expression').
```

secure NodeJS Application
```
=>	Use SSL for communication
=>	Always escape user data
=>	Use prepared statements for database queries
=>	Remove sensitive information from Request URLs
=>	Allow redirects only to whitelisted or hardcoded URLs
=>	Disable all unused API routes
=>	CSRF Token should be present in all pages that create or update data
=>	Provide log off or exit functionality which expires session(PassportJS)
=>	HTTP Only Cookie Attribute for all pages and links
=>	AUTOCOMPLETE=off attribute for sensitive HTML form input fields
=>	Set your X-Frame-Options set to DENY, SAMEORIGIN, or ALLOW-FROM	
=>	Set Security HTTP Headers(Helmet)
=>	Protect from Brute Force and DDOS Attacks(rate-limit)
=>	Don't use eval
=>	Always use strict mode
=>	Handle errors carefully
=>	Do a static analysis of your codebase(ESLint)
=>	Don't run your processes with superuser rights
=>	Set up the obligatory HTTP headers
=>	Do proper session management
=>	Set cookie scope
=>	Look for vulnerabilities with Retire.js
=>	Audit your modules with the Node Security Platform CLI
```

Difference between async.each and async.eachSeries
```
*  in the async.each all the async request calls are made at once and allowed to proceed in parallel.
*  The AsyncEachSeries wait for each operation to complete before moving into next while AsyncEach do things in parallel.
*  The difference with async.eachSeries is that each iteration will wait for the async operation to 
   complete before starting the next one.
```

Explain Modules in Node Js ?
```
Modules are reusable block of code whose existence does not impact other code in any way. 
It is not supported by Javascript. Modules are introduced in ES6. Modules are important 
for Maintainability, Reusability, and Namespacing of Code.
```

ES6 Features Every 
```
Default Parameters in ES6
Template Literals in ES6
Multi-line Strings in ES6
Destructuring Assignment in ES6
Enhanced Object Literals in ES6
Arrow Functions in ES6
Promises in ES6
Block-Scoped Constructs Let and Const
Classes in ES6
Modules in ES6
```

What is the difference between readFile vs createReadStream in Node.js?
```
readFile — is for asynchronously reads the entire contents of a file. It will read the file completely 
into memory before making it available to the User. readFileSync is synchronous version of readFile.

createReadStream — It will read the file in chunks of the default size 64 kb which is specified before hand.
```

What is Tracing in Node.js?
```
Tracing provides a mechanism to collect tracing information generated by V8, Node core and 
userspace code in a log file. Tracing can be enabled by passing the --trace-events-enabled flag 
when starting a Node.js application. Running Node.js with tracing enabled will produce log 
files that can be opened in the chrome://tracing tab of Chrome.
```

What is the use of Timers is Node.js?
```
The Timers module in Node.js contains functions that execute code after a set period of time. 
Timers do not need to be imported via require(), since all the methods are available globally 
to emulate the browser JavaScript API.
```

What is the use of DNS module in Node.js?
```
dns module which provide underlying system's name resolution and DNS look up facilities. 
DNS module consists of an asynchronous network wrapper.
dns.lookup(adress, options, callback) - The dns lookup method takes any website address as 
its first parameter and returns the corresponding first IPV4 or IPV6 record.
```