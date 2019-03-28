# Memcached Interview Questions


Memcached
```
=>	Memcached is Written in 'C' Language
=>	Free & open source,
=>	high-performance, distributed memory object caching system.
=>	Memcached server is a big hash table.
=>	intended for use in speeding up dynamic web applications 
=>	Memcached is an in-memory key-value store for small chunks of arbitrary data 
	(strings, objects) from results of database calls, API calls, or page rendering.
=>	caching data and objects in RAM to reduce the number of times an external data
	source must be read.
=>  The servers keep the values in RAM; if a server runs out of RAM, 
	it discards the oldest  values.
=>	It significantly reduces the database load
=>	It is perfectly efficient for websites with high database load.
=>	It is a client-server application over TCP or UDP.
=>	Memcached is not a database
=>	Memcached is not application-specific
=>	If you are using Memcached then data is lost with a restart and rebuilding cache is a costly process.
=>	Another scenario in which Memcached has an advantage over Redis is in scaling.
	Because Memcached is multithreaded, you can easily scale up by giving it more computational resources.
=>	Memcached is a simple volatile cache server.
=>	memcached is atomic as well,
=>	No persistence of data. Everything goes away when you restart it.
=>	No security support
=>	No events on cache changes
=>	used to speed up dynamic web applications by reducing the database load.
=>	It is a key-value dictionary of strings, objects, etc.
=>	Memcached is not a persistent data store.
=>	Memcached and Redis both keep all data in RAM.
```
	
How Memcached Works
```
- Try to get to get the detail of user, Browser send the request to application.
- Application call the Memcached for particular user.
- If Result found in Memcached, Return the result from Memcached.
- If Result Not found in Not Memcached, Application send the request to database and   save the result in memcached.
- Each Memcached have one unique key.
- Get/Set the data works on the behalf of key.
- you can also delete one or more keys.
- You can also assign tags to one/more keys.
```	

key features of Memcached
```
*	It is open source.
*	Memcached server is a big hash table.
*	It significantly reduces the database load
*	It is perfectly efficient for websites with high database load.
*	It is distributed under Berkeley Software Distribution (BSD) license.
*	It is a client-server application over TCP or UDP.
```

Memcached vs Redis
```
*	Both Memcached and Redis serve as in-memory, key-value data stores, although Redis is more accurately 
	described as a data structure store.
*	Redis is more powerful, more popular, and better supported than memcached.
*	Memcached can only do a small fraction of the things Redis can do.
*	Redis includes cluster support and comes with high availability tools (redis-sentinel) 
*	Both Memcached and Redis belong to the NoSQL family of data management solutions, and both are based on a key-value data model.
*	They both keep all data in RAM, which of course makes them supremely useful as a caching layer.
*	Redis has more features,more powerful and flexible than Memcached.
*	Memcached could be preferable when caching relatively small and static data, such as HTML code fragments.
*	Redis, which is mostly single-threaded, can scale horizontally via clustering without loss of data. 
	Clustering is an effective scaling solution, but it is comparatively more complex to set up and operate.
*	Memcached is multithreaded, you can easily scale up by giving it more computational resources, 
	but you will lose part or all of the cached data.
```

Installing Memcached on Ubuntu
```
=>	sudo apt-get update
=>	sudo apt-get install memcached
=>	ps aux | grep memcached
=>	memcached -p 11111 -U 11111 -u user -d
=>	telnet HOST PORT
	get key
	set key 0 900 4
	add key 0 900 4
	replace key 0 900 4
	append key 0 900 4
	prepend key 0 900 4
	delete key 
```