# Web Developer Interview Questions


difference between stateless and stateful protocol
```
A stateful server keeps state between connections. A stateless server does not. 
A stateless protocol does not require the server to retain session information or status about each communicating 
partner for the duration of multiple requests. In contrast, a protocol that requires keeping of the internal 
state on the server is known as a stateful protocol.
```
	
Is HTTP stateful or stateless?
```
HTTP is a stateless protocol, in other word the server will forget everything related to client/browser state. 
Although web applications have made it virtually look like stateful. A stateless protocol can be forced to 
behave as if it were stateful.
```
	
diff between angular and jquery
```
=> they both work at different levels.
=> jQuery => dealing with the DOM, finding elements, changing UI, and so on.
=> Angular => to add MVC concepts to front end engineering.
```
	
Why FTP is stateful protocol?
```
the FTP protocol is stateful: the client establishes a Control Connection for the duration of an FTP session 
that typically spans multiple data transfers. FTP uses a separate TCP connection for data transfer.
```	

How do CSRF tokens work?
```
=> Server sends the client a token.
=> Client submits a form with the token.
=> The server rejects the request if the token is invalid.
```		

what is protocol ?
```
A protocol is a set of rules that governs the communications between computers on a network. 
In order for two computers to talk to each other, they must be speaking the same language.
```
	
stateless protocol
```
=>	A stateless protocol does not require the server to retain session information or status about each 
	communications partner for the duration of multiple requests. 
=>	Stateless means there is no record of previous interactions and each interaction request has to be 
	handled based entirely on information that comes with it.
=>	A stateless server keeps no state information.
```

statefull protocol
```
=>	a protocol that requires keeping of the internal state on the server is known as a stateful protocol.
=>	Stateful means the computer or program keeps track of the state of interaction, 
	usually by setting values in a storage field designated for that purpose. 
=>	A stateful server remembers client data (state) from one request to the next. 
```
	
Why FTP is stateful protocol?
```
=>  the FTP protocol is stateful: the client establishes a Control Connection for the duration of an FTP
    session that typically spans multiple data transfers.
```
	
Why is http called a stateless protocol?
```
=>	HTTP is called a stateless protocol because each command is executed independently, without any knowledge of the 
	commands that came before it. This is the main reason that it is difficult to implement Web sites that react 
	intelligently to user input.
```

Is TCP IP stateless?
```
=> The TCP protocol is a stateful protocol because of what it is, not because it is used over IP or 
	because HTTP is built on top of it
```	

What is meant by stateless application?
```
=>	A stateless app is an application program that does not save client data generated in one session 
	for use in the next session with that client. In contrast, a stateful application saves data 
	about each client session and uses that data the next time the client makes a request.	
```

session and cookies difference
```
=>  The main difference between a session and a cookie is that session data is stored on the server, 
	whereas cookies store data in the visitor's browser. Sessions are more secure than cookies as it is stored in server.
	Cookie can be turn off from browser.
=> A cookie is a bit of data stored by the browser and sent to the server with every request.
=> Cookies are stored in browser as text file format.
=> Cookies is stored limit amount of data. It is only allowing 4kb[4096bytes]
=> Cookies is not holding the multiple variable in cookies.
=> We can accessing the cookies values in easily. So it is less secure.
=> Destroy Cookies: If we Closing the browsers at the time. / Setting the cookie time to expire the cookie.
```

Sessions
```
=> Sessions are stored in server side.
=> It is stored unlimited amount of data.
=> It is holding the multiple variable in sessions.
=> Using unset() session, we will destroyed the sessions.
=>	Using session_destory(), we we will destroyed the sessions.
```

difference between soap and rest
```
=> REST stands for Representational State Transfer
=> SOAP stands for Simple Object Access Protocol.
=> SOAP does not support error handling but REST has built-in error handling.
=> REST is generally faster, lightweight, uses less bandwidth. and does not require XML parsing.
=> REST is designed to be stateless, and REST reads can be cached for better performance and scalability.
=> REST allows a greater variety of data formats, whereas SOAP only allows XML.
=> REST is an architecture. REST will give human-readable results. REST is stateless. REST services are easily cacheable.
=> SOAP is simple object access protocol that run on TCP/UDP/SMTP.
=> REST uses set of VERBs like HTTP's GET, POST, PUT, DELETE.
```

Google App Engine
```
App Engine is a Platform-as-a-Service. It means that you simply deploy your code, and the 
platform does everything else for you. For example, if your app becomes very successful, 
App Engine will automatically create more instances to handle the increased volume.
```

Google Compute Engine
```
Compute Engine is an Infrastructure-as-a-Service. You have to create and configure your 
own virtual machine instances. It gives you more flexibility and generally costs much less 
than App Engine. The drawback is that you have to manage your app and virtual machines yourself.
```

What is the YAML?
```
YAML is case sensitive.
The files should have .yaml as the extension.
YAML (YAML Ain't Markup Language) is a human-readable data serialization language.
YAML does not allow the use of tabs while creating YAML files; spaces are allowed instead
The purpose of a markup language is to define a structure of a document, and YAML does exactly that.
It is commonly used for configuration files, but could be used in many applications where data is being stored
```

What is the difference between YAML and JSON?
```
YAML, depending on how you use it, can be more readable than JSON
JSON is often faster and is probably still interoperable with more systems
Duplicate keys, which are potentially valid JSON, are definitely invalid YAML.
YAML has a ton of features, including comments and relational anchors. 
YAML syntax is accordingly quite complex, and can be hard to understand.
```