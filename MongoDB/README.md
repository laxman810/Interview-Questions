# MongoDB Interview Questions

Explain what is MongoDB?
```
* Mongo-DB is a document database which provides high performance, high availability and easy scalability.
```

What makes MongoDB the best?
```
MongoDB is considered to be best NoSQL database because of :Document-oriented (DO)
High performance (HP)
High availability (HA)
Easy scalability
Rich query language
```

Advantages of MongoDB
```
* Schema less − MongoDB is a document database in which one collection holds different documents. 
  Number of fields, content and size of the document can differ from one document to another.
* Structure of a single object is clear.
* No complex joins.
* Deep query-ability. MongoDB supports dynamic queries on documents using a document-based query 
  language that's nearly as powerful as SQL.
* Tuning.
* Ease of scale-out − MongoDB is easy to scale.
* Conversion/mapping of application objects to database objects not needed.
* Uses internal memory for storing the (windowed) working set, enabling faster access of data.
```

Why Use MongoDB?
```
* Document Oriented Storage − Data is stored in the form of JSON style documents.
* Index on any attribute
* Replication and high availability
* Auto-sharding
* Rich queries
* Fast in-place updates
* Professional support by MongoDB
```

Where to Use MongoDB?
```
* Big Data
* Content Management and Delivery
* Mobile and Social Infrastructure
* User Data Management
* Data Hub
```

Disadvantages Of MongoDB
```
a. Joins not Supported
b. High Memory Usage
c. Limited Data Size
d. Limited Nesting
e. No Transctions
f. Memory Limitation	
```

MongoDB - ObjectId
```
An ObjectId is a 12-byte BSON type having the following structure −
* The first 4 bytes representing the seconds since the unix epoch
* The next 3 bytes are the machine identifier
* The next 2 bytes consists of process id
* The last 3 bytes are a random counter value
```

What is “Namespace” in MongoDB?
```
	MongoDB stores BSON (Binary Interchange and Structure Object Notation) objects in the collection. 
The concatenation of the collection name and database name is called a namespace.
```

What is sharding in MongoDB?
```
	The procedure of storing data records across multiple machines is referred as Sharding. 
It is a MongoDB approach to meet the demands of data growth. It is the horizontal partition of data 
in a database or search engine. Each partition is referred as shard or database shard.
```

Explain what is a replica set?
```
	A replica set is a group of mongo instances that host the same data set. In replica set, one node is 
primary, and another is secondary. From primary to the secondary node all data replicates.
```

How replication works in MongoDB?
```
	Across multiple servers, the process of synchronizing data is known as replication. It provides 
redundancy and increase data availability with multiple copies of data on different database server. 
Replication helps in protecting the database from the loss of a single server.
```

To do safe backups what is the feature in MongoDB that you can use?
```
Journaling is the feature in MongoDB that you can use to do safe backups.
```

How does MongoDB provide consistency?
```
MongoDB uses the reader-writer locks, allowing simultaneous readers to access any supply like a 
database or any collection. But always offers private access to singles writes.
```

What is Aggregation in MongoDB?
```
Aggregations are operations that process data records and return computed results.
Aggregation operations group values from multiple documents together, and can perform a variety 
of operations on the grouped data to return a single result.
MongoDB provides three ways to perform aggregation:
the aggregation pipeline, the map-reduce function, and single purpose aggregation methods.
```

What is the use of Index in mongodb?
```
Indexes provide high performance read operations for frequently used queries.
```

What are Primary and Secondary Replica sets?
```
Primary and master nodes are the nodes that can accept writes. MongoDB's replication is 'single-master:' 
only one node can accept write operations at a time.
Secondary and slave nodes are read-only nodes that replicate from the primary.
```

What is the use of profiler?
```
Profiler is used to show the performance characteristics of every operation against the database.
```

What is vertical scaling?
```
Vertical scaling adds more CPU and storage resources to increase capacity.
```

Define horizontal scaling.
```
It divides the data set and distributes the data over multiple servers, or shards.
```

Define Mongodb projection.
```
Projection is used to select only necessary data.It did not select whole data of a document.
```

Does MongoDB need a lot of RAM?
```
No. MongoDB can be run even on a small amount of RAM. MongoDB dynamically allocates and de-allocates 
RAM based on the requirements of other processes.
```

Does MongoDB pushes the writes to disk immediately or lazily?
```
MongoDB pushes the data to disk lazily. It updates the immediately written to the journal but writing 
the data from journal to disk happens lazily.
```

What are Indexes in MongoDB?
```
Indexes support the efficient execution of queries in MongoDB. Without indexes, MongoDB must perform a collection 
scan, i.e. scan every document in a collection, to select those documents that match the query statement. If an 
appropriate index exists for a query, MongoDB can use the index to limit the number of documents it must inspect.
```

What happens if an index does not fit into RAM?
```
If the indexes do not fit into RAM, MongoDB reads data from disk which is relatively very 
much slower than reading from RAM.
```

What is a Storage Engine in MongoDB
```
A storage engine is the part of a database that is responsible for managing how data is stored on disk. 
For example, one storage engine might offer better performance for read-heavy workloads, 
and another might support a higher-throughput for write operations.
```

Which are the two storage engines used by MongoDB?
```
MongoDB uses MMAPv1 and WiredTiger.
```

Can one MongoDB operation lock more than one databases? If yes, how?
```
Yes. Operations like copyDatabase(), repairDatabase(), etc. can lock more than onne databases involved.
```

Explain what is GridFS in MongoDB?
```
For storing and retrieving large files such as images, video files and audio files GridFS is used. 
By default, it uses two files fs.files and fs.chunks to store the file’s metadata and the chunks.
GridFS has the capability to store files even greater than its document size limit of 16MB. 
GridFS divides a file into chunks and stores each chunk of data in a separate document, each of maximum size 255k.
```
	
Data Modeling In MongoDB
```
=>	Data in MongoDB has a flexible schema.
=>	MongoDB’s collections do not enforce document structure.
=>	This flexibility facilitates the mapping of documents to an entity or an object.
	Document Structure :
=>	There are two tools that allow applications to represent these relationships: 
	references and embedded documents.
	References : 
=>	References store the relationships between data by including links or references from one document to another. 
	Applications can resolve these references to access the related data. Broadly, these are normalized data models.
	Embedded Data :
=>	Embedded documents capture relationships between data by storing related data in a single document structure.
	MongoDB documents make it possible to embed document structures in a field or array within a document.
	These denormalized data models allow applications to retrieve and manipulate related data in a single database operation.
```

MongoDb Index Types
```
*	MongoDB provides a number of different index types
*	You can create indexes on any field or embedded field within a document or embedded document.
=>	Single Field Indexes
=>	Compound Indexes
=>	Multikey Indexes
=>	Geospatial Indexes and Queries
=>	Text Indexes
=>	Hashed Index
```

How big can a MongoDB be?
```
BSON Documents. The maximum BSON document size is 16 megabytes. The maximum document size helps 
ensure that a single document cannot use excessive amount of RAM or, during transmission, excessive 
amount of bandwidth. To store documents larger than the maximum size, MongoDB provides the GridFS API.
```