# HAProxy Interview Questions


Explain what is Nginx?
```
Nginx is a web server and a reverse proxy server for HTTP, HTTPS, SMTP, POP3 and IMAP protocols.
HAProxy allows a webserver to spread incoming requests across multiple endpoints.
HAProxy stands for High Availability Proxy.
HAProxy is a popular open source software TCP/HTTP Load Balancer and proxying solution.
HAProxy can be run on Linux, Solaris, and FreeBSD.
HAProxy can load balance HTTP and TCP servers.
HAProxy most common use is to improve the performance and reliability of a server 
environment by distributing the workload across multiple servers.
```

Mention some special features of Nginx?
```
Reverse proxy/ L7 Load Balancer
Embedded Perl interpreter
On the fly binary upgrade
Useful for re-writing URLs and awesome PCRE support
```

Access Control List (ACL)
```
ACLs are used to test some condition and perform an action based on the test result.
Use of ACLs allows flexible network traffic forwarding based on a variety of factors 
like pattern-matching and the number of connections to a backend.
Example of an ACL: acl url_blog path_beg /blog
```

Backend
```
A backend is a set of servers that receives forwarded requests. 
A backend can be defined by: 1) which load balance algorithm to use 2) a list of servers and ports.
A backend can contain one or many servers in it--generally speaking, adding more servers to 
your backend will increase your  potential load capacity by spreading the load over multiple servers
Example :
	backend web-backend
	   balance roundrobin
	   server web1 web1.yourdomain.com:80 check
	   server web2 web2.yourdomain.com:80 check
```

Frontend
```
A frontend defines how requests should be forwarded to backends. 
Frontends are defined in the frontend section of the HAProxy configuration.
Their definitions are composed of the following components:
	1) a set of IP addresses and a port (e.g. 10.1.1.7:80, *:443, etc.)
	2) ACLs
	3) use_backend rules, which define which backends to use depending on which ACL conditions are matched, 
	   and/or a default_backend rule that handles every other case
Example :
	frontend http
	  bind *:80
	  mode http
	  acl url_blog path_beg /blog
	  use_backend blog-backend if url_blog
	  default_backend web-backend
```
  
Types of Load Balancing :
```
Layer 4 Load Balancing(transport layer)
Layer 7 Load Balancing(application layer)
```
	
Load Balancing Algorithms
```
roundrobin
leastconn
source
Sticky Sessions
Health Check
```

Other Solutions
```
Linux Virtual Servers (LVS)
Nginx 
```

FILES & FOLDERS
```
1. /usr/sbin/haproxy
	Default location of the binary.
2. /usr/share/doc/haproxy
	Built-in documentation.
3. /etc/init.d/haproxy
	init script used to control the HAProxy process/service.
4. /etc/default/haproxy
	File that is sourced by both the initscript for haproxy.cfg file location.
5. /etc/haproxy
	Default location of the haproxy.cfg file which determines all functions of HAProxy.
```

What is Server Load Balancing?
```
Server Load Balancing (SLB) provides network performance and content delivery by 
implementing a series of algorithms and priorities to respond to the specific 
requests made to the network. In simple terms, SLB distributes clients to a group 
of servers and ensures that clients are not sent to failed servers.
```
