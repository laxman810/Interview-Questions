## Node RESTful APIs Design Guidelines : 

 Instead of using long URLs making  things complicated we can use `HTTP methods` and it's `status codes` to represent different-different `CRUD operations`. This is how we create `RESTful APIs`. [Click here to go to full tutorial !](https://hackernoon.com/restful-api-designing-guidelines-the-best-practices-60e1d954e7c9)
 - [Video to understand RESTful APIs!](https://www.youtube.com/watch?v=BRdcRFvuqsE&list=PL4cUxeGkcC9jBcybHMTIia56aV21)


## JavaScript Clean Coding Best Practices
Writing clean code is what you must know and do in order to call yourself a professional developer.[Click here to go to full tutorial !](https://blog.risingstack.com/javascript-clean-coding-best-practices-node-js-at-scale/)

## Introduction To Nodejs Tutorial
This video series will take you to the basic of nodejs and special contains all the topics which are simply explained. Please do not follow it's coding practices those are just demo to explain the topics.
[Click here to go to full tutorial](https://www.youtube.com/playlist?list=PL4cUxeGkcC9gcy9lrvMJ75z9maRw4byYp)

Modules included are following : 
- `V8 Engine`
- `Global Object`
- `Function Expression`
- `Modules and require()`
- `Event Emitter`
- `FS`
- `Streams and Buffers`
- `Pipes`
- `Serving JSON`
- `Templates`
- `Express with demo Example`


## Understanding The Nodejs Event Loop
This will take you to the concept of Async and I/O non-blocking nature of Nodejs. [Click here to go to full tutorial !](https://blog.risingstack.com/node-js-at-scale-understanding-node-js-event-loop/)

## Debugging, Async Memory Leaks & CPU Profiling
Debugging, understanding/using Async programming, handling callbacks and memory leaks are amongst the greatest pain-points one would face on her/his journey to become a Node Hero. [Click here to go to full tutorial !](https://blog.risingstack.com/node-js-tutorial-debugging-async-memory-leaks-cpu-profiling/)


# **Nodejs Important Modules**

* # Assert

The assert module provides a way of testing expressions. If the expression evaluates to 0, or false, an assertion failure is being caused, and the program is terminated.
- In simple words, we can use this module to perform `comparision between two expressions` _like: comparing two values or values returned by two different functions_

- _It is mostly used in unit testing with testing modules like `Mocha`._

### **Assert Methods**

Method | Description
------ | -----------
assert() | Checks if a value is true. Same as assert.ok()
deepEqual() | Checks if two values are equal
deepStrictEqual() | Checks if two values are equal, using the strict equal operator (===)
equal() | Checks if two values are equal, using the equal operator (==)
fail() | Throws an Assertion Error
ifError() | Throws a specified error if the specified error evaluates to true
notDeepEqual() | Checks if two values are not equal
notDeepStrictEqual() | Checks if two values are not equal, using the strict not equal operator (!==)
notEqual() | Checks if two values are not equal, using the not equal operator (!=)
notStrictEqual() | Checks if two values are not equal, using the strict not equal operator (!==)
ok() | Checks if a value is true
strictEqual() | Checks if two values are equal, using the strict equal operator (===)

- Following is the very simple use of assertion : 

```javascript

var assert = require('assert');
assert(5 > 7);

// Output  : AssertionError: false == true

```
- `AssertionError`
    - A subclass of Error that indicates the failure of an assertion. All errors thrown by the assert module will be instances of the AssertionError class.
    - We can also create custom AssertionError.


* # Async Hooks

The async_hooks module provides an API to register callbacks tracking the lifetime of asynchronous resources created inside a Node.js application. It can be accessed using:

- Above line simply means that we can get `hooks of lifecycle of Async functions (Promises)`.
- These are some states of promise lifecycle. =>  **init, before, after, destroy, promiseResolve**

_We don't use this module much so i'm just mentioning the method of creating Async Lifecycle Hooks._


> ##   **async_hooks.createHook**
> 
> Added in: v8.1.0
> 
> callbacks The Hook Callbacks to register
> 
> `init`  The init callback.
> 
> `before`  The before callback.
> 
> `after`  The after callback.
> 
> `destroy`  The destroy callback.
> 
> Returns:  Instance used for disabling and enabling hooks 
> 
> Registers functions to be called for different lifetime events of each async operation.
> 
> The callbacks init()/before()/after()/destroy() are called for the respective asynchronous event during a resource's lifetime.
> 
> All Options are optional.


- Example : 

```javascript
const async_hooks = require('async_hooks');

const asyncHook = async_hooks.createHook({ init });

// init is called during object construction. The resource may not have
// completed construction when this callback runs, therefore all fields of the
// resource referenced by "asyncId" may not have been populated.
function init(asyncId, type, triggerAsyncId, resource) { }

```


* # Child Process

    The child_process module provides the ability to spawn child processes in a manner that is similar, but not identical, to popen(3). This capability is primarily provided by the child_process.spawn() function

    _**Note :** `child_process` is not a `thread` so don't be confused between them._

    We can easily spin a `child process` using Node’s `child_process module` and those child processes can easily communicate with each other with a `messaging system`.

_The child_process module enables us to access `Operating System functionalities` by running any system command inside a, well, child process._

## [Click here for better understanding Child Process.](https://medium.freecodecamp.org/node-js-child-processes-everything-you-need-to-know-e69498fe970a)

* # Cluster

    **_A single instance of Node.js runs in a `single thread`. To take advantage of `multi-core systems`, the user will sometimes want to launch a cluster of Node.js processes to handle the load._**

    Cluster means group of processes which have one main process called `Master`.

    _The cluster module allows easy creation of child processes that all share server ports._

```javascript
const cluster = require('cluster');
const http = require('http');
const numCPUs = require('os').cpus().length;

if (cluster.isMaster) {
  console.log(`Master ${process.pid} is running`);

  // Fork workers.
  for (let i = 0; i < numCPUs; i++) {
    cluster.fork();
  }

  cluster.on('exit', (worker, code, signal) => {
    console.log(`worker ${worker.process.pid} died`);
  });
} else {
  // Workers can share any TCP connection
  // In this case it is an HTTP server
  http.createServer((req, res) => {
    res.writeHead(200);
    res.end('hello world\n');
  }).listen(8000);

  console.log(`Worker ${process.pid} started`);
}
```

_Running Node.js will now share port 8000 between the workers:_

```console
$ node server.js
Master 3596 is running
Worker 4324 started
Worker 4520 started
Worker 6056 started
Worker 5644 started
```


* # Command Line Options

    Node.js comes with a variety of CLI options. These options expose built-in debugging, multiple ways to execute scripts, and other helpful runtime options.


There are two types of options we can pass :

1. **`CLI Options`**
1. **`Environment variables`**

> ### **`CLI Options`**
> 
>   # -
>> Alias for stdin, meaning that the script will be read from stdin, and the rest of the options are passed to that script.
>   # --
>> Indicate the end of node options. Pass the rest of the arguments to the script. If no script filename or eval/print script is supplied prior to this, then the next argument will be used as a script filename.
>   ### **--inspect**
>> This is used for debugging and we can get great debugging with this in Chrome browser becuse it provides very rich options and DevTools.


> ### **`Environment variables`**
>
> ### NODE_DEBUG=module[,…]
>
>> ','-separated list of core modules that should print debug information.
>
> ### NODE_ICU_DATA=file
> 
>> Used to provide `Multi Languange Support` Data path for ICU (Intl object) data. Will extend linked-in data when compiled with small-icu support.

> _There are many other options. To view this documentation as a manual page in a terminal, run `man node`._

* # Console

    The console module provides a simple debugging console that is similar to the JavaScript console mechanism provided by web browsers.

The module exports two specific components:

- A Console class with methods such as `console.log()`, `console.error()` and `console.warn()` that can be used to write to any `Node.js stream`.
- A global console instance configured to write to `process.stdout` and `process.stderr`. The global console can be used without calling `require('console')`.

- **It's very simple see following Example :**

```javascript
console.log('hello world');
// Prints: hello world, to stdout
console.log('hello %s', 'world');
// Prints: hello world, to stdout
console.error(new Error('Whoops, something bad happened'));
// Prints: [Error: Whoops, something bad happened], to stderr

const name = 'Will Robinson';
console.warn(`Danger ${name}! Danger!`);
// Prints: Danger Will Robinson! Danger!, to stderr
```

* # Crypto

    The crypto module provides cryptographic functionality that includes a set of wrappers for OpenSSL's hash, HMAC, cipher, decipher, sign, and verify functions.

- Mostly we know that there are two types of cyptography methods we use are following :
+ Encryption/Decryption
+ Hashing

> - _OpenSSL is a robust, commercial-grade, and full-featured toolkit for the Transport Layer Security (TLS) and Secure Sockets Layer (SSL) protocols. It is also a general-purpose cryptography library._

* Now crypto is used for lots of things as above mentioned. but right now we just take a simple hashing example to unbderstand it's use.

```javascript
const crypto = require('crypto');

const secret = 'abcdefg';
const hash = crypto.createHmac('sha256', secret)
                   .update('I love cupcakes')
                   .digest('hex');
console.log(hash);
// Prints:
//   c0fa1bc00531bd78ef38c628449c5102aeabd49b5dc3a2a516ea6ea959d6658e
```

* # Debugger

    I've mentioned `--inspect` option in `CLI module`, well Node.js includes an `out-of-process debugging utility` accessible via a `V8 Inspector` and `built-in debugging client`. To use it, start Node.js with the inspect argument followed by the path to the script to debug; a prompt will be displayed indicating successful launch of the debugger:

```console
$ node inspect myscript.js
< Debugger listening on ws://127.0.0.1:9229/80e7a814-7cd3-49fb-921a-2e02228cd5ba
< For help, see: https://nodejs.org/en/docs/inspector
< Debugger attached.
Break on start in myscript.js:1
> 1 (function (exports, require, module, __filename, __dirname) { global.x = 5;
  2 setTimeout(() => {
  3   console.log('world');
debug>

```

* _Inserting the statement `debugger;` into the source code of a script will enable a breakpoint at that position in the code:_

```javascript

// myscript.js
global.x = 5;
setTimeout(() => {
  debugger;
  console.log('world');
}, 1000);
console.log('hello');

```

> * **Stepping**
>
>> Once you are in `Commandline debugging mode` following options will be useful to control the program flow for debugging
>
>> `cont`, `c` - Continue execution
>
>> `next`, `n` - Step next
>
>> `step`, `s` - Step in
>
>> `out`, `o` - Step out
>
>> `pause` - Pause running code (like pause button in Developer Tools)
>
>> `repl` - To get in to _Read Eval Print Loop_ used to observe varible values.

* # DNS

    Usually DNS acrinomy stands for two different full forms 
    * **`Domain Name System`** : _The system by which Internet domain names and addresses are tracked and regulated._
    * **`Domain Name Service`** :  _A distributed directory that resolves human-readable hostnames, such as www.dyn.com, into machine-readable IP addresses like 50.16.85.103._

**_In simple words DNS module here is used for Domain Name Service purposes, `to resolve domain name to it's address` (can be IPV4 or IPV6)._**

    The dns module contains functions belonging to two different categories:

    1) Functions that use the underlying operating system facilities to perform name resolution, and that do not necessarily perform any network communication. This category contains only one function: dns.lookup(). Developers looking to perform name resolution in the same way that other applications on the same operating system behave should use dns.lookup().

    For example, looking up iana.org.

```javascript
const dns = require('dns');

dns.lookup('iana.org', (err, address, family) => {
  console.log('address: %j family: IPv%s', address, family);
});
// address: "192.0.43.8" family: IPv4
```

    2) Functions that connect to an actual DNS server to perform name resolution, and that always use the network to perform DNS queries. This category contains all functions in the dns module except dns.lookup(). These functions do not use the same set of configuration files used by dns.lookup() (e.g. /etc/hosts). These functions should be used by developers who do not want to use the underlying operating system's facilities for name resolution, and instead want to always perform DNS queries.

    Below is an example that resolves 'archive.org' then reverse resolves the IP addresses that are returned.

```javascript
const dns = require('dns');

dns.resolve4('archive.org', (err, addresses) => {
  if (err) throw err;

  console.log(`addresses: ${JSON.stringify(addresses)}`);

  addresses.forEach((a) => {
    dns.reverse(a, (err, hostnames) => {
      if (err) {
        throw err;
      }
      console.log(`reverse for ${a}: ${JSON.stringify(hostnames)}`);
    });
  });
});
```

* # Errors

        Applications running in Node.js will generally experience four categories of errors:

    * Standard JavaScript errors such as `<EvalError>`, `<SyntaxError>`, `<RangeError>`, `<ReferenceError>`, `<TypeError>`, and `<URIError>`.
    * System errors triggered by `underlying operating system constraints` such as attempting to open a file that does not exist or attempting to send data over a closed socket.
    * User-specified errors triggered by application code.
    * `AssertionErrors` are a special class of error that can be triggered when Node.js detects an `exceptional logic violation that should never occur`. These are raised typically by the assert module.
    * All JavaScript and System errors raised by Node.js inherit from, or are instances of, the standard JavaScript `<Error> class` and are guaranteed to provide at least the properties available on that class.

_All JavaScript errors are handled as exceptions that immediately generate and throw an error using the standard JavaScript throw mechanism. These are handled using the **`try…catch`** construct provided by the JavaScript language._

```javascript
// Throws with a ReferenceError because z is undefined
try {
  const m = 1;
  const n = m + z;
} catch (err) {
  // Handle the error here.
}
```

* # Events

    Much of the Node.js core API is built around `an idiomatic asynchronous event-driven architecture` in which certain kinds of objects (called "emitters") emit named events that cause Function objects ("listeners") to be called.

**_All objects that emit events are instances of the `EventEmitter class`. These objects expose an `eventEmitter.on()` function that allows one or more functions `to be attached to named events emitted by the object`. Typically, event names are camel-cased strings but any valid JavaScript property key can be used._**

_The following example shows a simple EventEmitter instance with a single listener. The eventEmitter.on() method is used to register listeners, while the eventEmitter.emit() method is used to trigger the event._

```javascript
const EventEmitter = require('events');

class MyEmitter extends EventEmitter {}

const myEmitter = new MyEmitter();
myEmitter.on('event', () => {
  console.log('an event occurred!');
});
myEmitter.emit('event');
```

* # HTTP

    The HTTP interfaces in Node.js are designed to support many features of the protocol which have been traditionally difficult to use. In particular, large, possibly chunk-encoded, messages. `The interface is careful to never buffer entire requests or responses` — the user is able to stream data.

**_In simple words it's used to `create http Server` and perform other operations which we perform using http protocol like `sendind and recieving data` (request & response)._**

_There are other things which we can do with http module for Advance level do not worry about it right now.Just remember that we can create http Agent which wan be useful for performing even soket level operations._

* **Example :**

```javascript
const http = require('http');

// Create an HTTP Server
const server = http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('Hello World!');
});

server.listen(1337, '127.0.0.1', () => {
    console.log("listening on : 1337");
});
```

* # HTTPS

    HTTPS is the HTTP protocol over TLS/SSL. In Node.js this is implemented as a separate module.

_We all feel safe when that lock logo appears in the URL bar. Well that is when `Transport Layer Security`(if you remember from OSI 7 layers) is used with Http._

**_To create Https server we need `SSL Certificates` which are assigned by `CA (Certification Authority)` and using that we can create Https Server._**

* **Example:**

```javascript
const https = require('https');
const fs = require('fs');

const options = {
  key: fs.readFileSync('test/fixtures/keys/agent2-key.pem'),
  cert: fs.readFileSync('test/fixtures/keys/agent2-cert.pem')
};

https.createServer(options, (req, res) => {
  res.writeHead(200);
  res.end('hello world\n');
}).listen(8000);
```

* # Internationalization Support  

    Locale-sensitive or Unicode-aware functions in the [ECMAScript Language Specification](https://tc39.github.io/ecma262/):

    * `String.prototype.normalize()`

    * `String.prototype.toLowerCase()`

    * `String.prototype.toUpperCase()`

    All functionality described in the [ECMAScript Internationalization API Specification](https://tc39.github.io/ecma402/) (aka ECMA-402):

_Well, **When we want to add multi language support and Unicode awarenes.** we use this module called **`Intl`**._

I'm not making this complex to confuse you just explaining the basic things you should know.
First of all Lets talk about ICU.

 * **`ICU (International Components for Unicode)`**: It is used for `Unicode and globalization support for software applications`. It is a mature, widely used set of C/C++ and Java libraries providing Unicode and Globalization support for software applications. ICU is widely portable and gives applications the same results on all platforms and between C/C++ and Java software.

    _To control how ICU is used in Node.js, four configure options are available during compilation._

    `--with-intl=none/--without-intl`

    `--with-intl=system-icu`

    `--with-intl=small-icu (default)`

    `--with-intl=full-icu`


```javascript
const january = new Date(9e8);
const english = new Intl.DateTimeFormat('en', { month: 'long' });
const spanish = new Intl.DateTimeFormat('es', { month: 'long' });

console.log(english.format(january));
// Prints "January"
console.log(spanish.format(january));
// Prints "M01" on small-icu
// Should print "enero"
```

_Take above example, Run that example with simple `node fileName.js` command which will not give you any different output i mean you will not get the output mentioned in code comments._

_You have to specify `icu type` to get desired output. because by default it just takes `system-icu` type which doesn't supports spanish._

_Now, install `full-icu` module using `npm install full-icu` and then run program with `node --icu-data-dir="./node_modules/full-icu" fileName.js`._

* # Process

    The process object is a global that provides `information about, and control over, the current Node.js process`. As a global, it is always available to Node.js applications without using `require()`.

    _The process object is an instance of `EventEmitter`._

    We know about `process.env` which is used to set environment variable for that node process.

    There are lots of process lifecycle hooks are available which we can used to `perform perticular operation on perticular event` are as following.
    * Event: `beforeExit`
    
    * Event: `disconnect`

    * Event: `exit`

    * Event: `message`

    * Event: `multipleResolves`

    * Event: `rejectionHandled`

    * Event: `uncaughtException`

_Handling Error centralized is a good idea but using `uncaughtException` hook to hadle error is a bed idea because Unhandled exceptions inherently mean that an application is in an `undefined state`. Attempting to resume application code without properly recovering from the exception can cause `additional unforeseen and unpredictable issues`._

* # Zlib

    _The zlib module provides compression functionality implemented using Gzip and Deflate/Inflate, as well as Brotli._

Compressing or decompressing a stream (such as a file) can be accomplished by piping the source stream data through a zlib stream into a destination stream:

```javascript

const zlib = require('zlib');
const gzip = zlib.createGzip();
const fs = require('fs');
const inp = fs.createReadStream('input.txt');
const out = fs.createWriteStream('input.txt.gz');

inp.pipe(gzip).pipe(out);

```