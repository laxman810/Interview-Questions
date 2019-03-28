# MONGODB CRASH COURSE

* # Introduction

    There are two types of DBMSs are available for data storing are `SQL` and `NoSQL`. People who had worked with Database Systems like MySQL or MS SQL know very well about SQL based database systems those are called RDBMS.
    where we can manage `Relationship` between two entities.

    When we talk about NoSQL databases they are like data structures which are used to store our data.Mongodb is
    also NoSQL database._To understand simply, they are just like file systems insted of files they store our data and they are now also able to `manage relationship` between entities._

    * ## Understanding Mongodb :  

     MongoDB is an open-source, document database designed for ease of development and scaling.

     Let's break down above sentence to understand mongodb,
      **`open source`** is understood by everyone.
      **`document database`** that means here we store `JSON Objects` in SQL we call it record which is **Record about perticular entitiy** raw of table. Here we call it `document`.Now we store so many records in one table, In mongodb, we call table a `Collection`.

    So,  `Record` in SQL is called `Document` in Mongodb. `Table` in SQL is called `Collection`. Don't worry database is database. 

    we will talk about scalling later and ease of development means made for developments.

    * ## Difference

    SQL	| NOSQL
    --- | -----
    RELATIONAL DATABASE MANAGEMENT SYSTEM (RDBMS) |	Non-relational or distributed database system.
    These databases have fixed or static or predefined schema |	They have have dynamic schema
    These databases are not suited for hierarchical data storage. |	These databases are best suited for hierarchical data storage.
    These databases are best suited for complex queries | These databases are not so good for complex queries
    Verticlly Scalable | Horizontally scalable

* # Install MongoDB
    [Click her to learn Instslling](https://docs.mongodb.com/manual/installation/)

* # Databases and Collections


    * ## Databases

    In MongoDB, databases hold `collections of documents`.

    To select a database to use, in the mongo shell, issue the use `db` statement, as in the following example:

    ```console
    use myDB
    ```

     * ### Create a Database

    _If a database does not exist, MongoDB creates the database when you first store data for that database._ As such, you can switch to a non-existent database and perform the following operation in the mongo shell:

    ```console
    use myNewDB
    db.myNewCollection1.insertOne( { x: 1 } )
    ```
    
    The `insertOne()` operation creates both the database `myNewDB` and the collection myNewCollection1 if they do not already exist.

    * ## Collections

    MongoDB stores `documents` in `collections`. Collections are `analogous to tables` in relational databases.

     * ### Create a Collection
    If a collection does not exist, MongoDB creates the collection when you first store data for that collection.

    ```console
    db.myNewCollection2.insertOne( { x: 1 } )
    db.myNewCollection3.createIndex( { y: 1 } )
    ```

    Both the `insertOne()` and the `createIndex()` operations create their respective collection if they do not already exist.

* # Documents

    Mongodb stores `documents` as discussed in introduction those are `BSON Documents` (Binary representation of JSON document). BSON contains more data types than JSON.[Click here to know more about BSON](http://bsonspec.org/)

    ![Document Image](https://docs.mongodb.com/manual/_images/crud-annotated-document.bakedsvg.svg)

    * ## Document Structure

    MongoDB documents are composed of field-and-value pairs and have the following structure:

    ```javascript
    {
    field1: value1,
    field2: value2,
    field3: value3,
    . . .
    fieldN: valueN
    }
    ```

    The value of a field can be any of the BSON data types, including other `documents`, `arrays`, and `arrays of documents`. For example, the following document contains values of varying types:

    ```javascript
    var mydoc = {
                _id: ObjectId("5099803df3f4948bd2f98391"),
                name: { first: "Alan", last: "Turing" },
                birth: new Date('Jun 23, 1912'),
                death: new Date('Jun 07, 1954'),
                contribs: [ "Turing machine", "Turing test", "Turingery" ],
                views : NumberLong(1250000)
                }

    ```

    The above fields have the following data types:

     * `_id` holds an `ObjectId`.
     * name holds an `embedded document` that contains the fields first and last.
     * birth and death hold values of the `Date type`.
     * contribs holds an `array of strings`.
     * views holds a value of the `NumberLong type`.

    _The field name `_id` is reserved for use as a primary key; its value must be unique in the collection, is immutable, and may be of any type other than an array._

    * ### ObjectId
    A field required in every MongoDB document. The _id field must have a `unique value`. You can think of the `_id` field as the `document’s primary key`. If you create a new document without an _id field, MongoDB automatically creates the field and assigns a unique BSON ObjectId.

    A special `12-byte BSON type` that guarantees uniqueness within the collection. The ObjectId is generated based on `timestamp`, `machine ID`, `process ID`, and a process-local incremental counter. MongoDB uses ObjectId values as the default values for _id fields.

    * ### Document Size Limit
     **The maximum BSON document size is 16 megabytes.**

* # MongoDB CRUD Operations

    CRUD operations create, read, update, and delete documents.

    * ## Create Operations
    Create or insert operations add new documents to a collection. _If the collection does not currently exist, insert operations will create the collection._

    MongoDB provides the following methods to insert documents into a collection:

    ```console
    db.collection.insertOne() 
    db.collection.insertMany()
    ```

    In MongoDB, insert operations target a single collection. All write operations in MongoDB are atomic on the level of a single document.

    The components of a MongoDB insertOne operations.

    * ## Read Operations
    Read operations retrieves documents from a collection; i.e. queries a collection for documents. MongoDB provides the following methods to read documents from a collection:

    ```console
    db.collection.find()
    ```

    You can specify query filters or criteria that identify the documents to return.

    * ## Update Operations
    Update operations modify existing documents in a collection. MongoDB provides the following methods to update documents of a collection:

    ```console
    db.collection.updateOne() 
    db.collection.updateMany() 
    db.collection.replaceOne() 
    ```

    In MongoDB, update operations target a single collection. All write operations in MongoDB are atomic on the level of a single document.

    You can specify criteria, or filters, that identify the documents to update. These filters use the same syntax as read operations.

    * ## Delete Operations
    Delete operations remove documents from a collection. MongoDB provides the following methods to delete documents of a collection:

    ```console
    db.collection.deleteOne() 
    db.collection.deleteMany() 
    ```

    In MongoDB, delete operations target a single collection. All write operations in MongoDB are atomic on the level of a single document.

    You can specify criteria, or filters, that identify the documents to remove. These filters use the same syntax as read operations.

* # Insert Documents

    * ## Insert a Single Document
    `db.collection.insertOne()` inserts a single document into a collection.

     The following example inserts a new document into the inventory collection. If the document does not specify an _id field, MongoDB adds the _id field with an ObjectId value to the new document.

    ```console
    db.inventory.insertOne(
    { item: "canvas", qty: 100, tags: ["cotton"], size: { h: 28, w: 35.5, uom: "cm" } }
    )
    ```
    * ## Insert Multiple Documents

     `db.collection.insertMany()` can insert multiple documents into a collection. Pass an array of documents to the method.

     The following example inserts three new documents into the inventory collection. If the documents do not specify an _id field, MongoDB adds the _id field with an ObjectId value to each document. 

    ```console
    db.inventory.insertMany([
    { item: "journal", qty: 25, tags: ["blank", "red"], size: { h: 14, w: 21, uom: "cm" } },
    { item: "mat", qty: 85, tags: ["gray"], size: { h: 27.9, w: 35.5, uom: "cm" } },
    { item: "mousepad", qty: 25, tags: ["gel", "blue"], size: { h: 19, w: 22.85, uom: "cm" } }
    ])
    ```

* # Query Documents

    * ## Select All Documents in a Collection
     To select all documents in the collection, pass an empty document as the query filter parameter to the find method. The query filter parameter determines the select criteria:

    ```console
    db.inventory.find( {} )
    ```

   * ## Specify Equality Condition
    To specify equality conditions, use `field`:`value` expressions in the query filter document:

    ```console
    db.inventory.find( { status: "D" } )
    ```


* # Update Documents

    * ## Update a Single Document
    The following example uses the `db.collection.updateOne()` method on the inventory collection to update the first document where item equals "paper":

    ```console
    db.inventory.updateOne(
    { item: "paper" },
    {
        $set: { "size.uom": "cm", status: "P" },
        $currentDate: { lastModified: true }
    }
    )
    ```

    * uses the `$set` operator to update the value of the `size.uom` field to `cm` and the value of the status field to `P`, 
    * uses the `$currentDate` operator to update the value of the lastModified field to the current date. If lastModified field does not exist, `$currentDate` will create the field.

    * ## Update Multiple Documents

     The following example uses the `db.collection.updateMany()` method on the inventory collection to update all documents where qty is less than 50:

    ```console
    db.inventory.updateMany(
    { "qty": { $lt: 50 } },
    {
        $set: { "size.uom": "in", status: "P" },
        $currentDate: { lastModified: true }
    }
    )
    ```

* # Delete Documents

     This page uses the following `mongo shell` methods:

    ```console
    db.collection.deleteMany()
    db.collection.deleteOne()
    ```

    The examples on this page use the `inventory` collection. To populate the inventory collection, run the following:

    ```console
    db.inventory.insertMany( [
    { item: "journal", qty: 25, size: { h: 14, w: 21, uom: "cm" }, status: "A" },
    { item: "notebook", qty: 50, size: { h: 8.5, w: 11, uom: "in" }, status: "P" },
    { item: "paper", qty: 100, size: { h: 8.5, w: 11, uom: "in" }, status: "D" },
    { item: "planner", qty: 75, size: { h: 22.85, w: 30, uom: "cm" }, status: "D" },
    { item: "postcard", qty: 45, size: { h: 10, w: 15.25, uom: "cm" }, status: "A" },
    ] );
    ````


    * ### Delete All Documents
    `To delete all documents from a collection`, pass an empty filter document {} to the db.collection.deleteMany() method.

    The following example deletes all documents from the inventory collection:

    ```console
    db.inventory.deleteMany({})
    ```
    
    * ### Delete All Documents that Match a Condition
     You can `specify criteria`, or `filters`, `that identify` the documents to delete. The filters use the same syntax as read operations.

     The following example removes all documents from the inventory collection where the status field equals "A":

    ```console
     db.inventory.deleteMany({ status : "A" })
    
    ```

    * ### Delete Only One Document that Matches a Condition
     To delete at most a single document that matches a specified filter (even though multiple documents may match the specified filter) use the db.collection.deleteOne() method.

    The following example deletes the first document where status is "D":

    ```console
    db.inventory.deleteOne( { status: "D" } )
    ```

* # Text Search

    * ## Example
    This example demonstrates how to build a text index and use it to find coffee shops, given only text fields.

    Create a collection stores with the following documents:

    ```console
    db.stores.insert(
    [
        { _id: 1, name: "Java Hut", description: "Coffee and cakes" },
        { _id: 2, name: "Burger Buns", description: "Gourmet hamburgers" },
        { _id: 3, name: "Coffee Shop", description: "Just coffee" },
        { _id: 4, name: "Clothes Clothes Clothes", description: "Discount clothing" },
        { _id: 5, name: "Java Shopping", description: "Indonesian goods" }
    ]
    )
    ```

    * ### Text Index
     MongoDB provides text indexes to support `text search queries` on string content. text indexes can include any field whose value is a string or an array of string elements.

     To perform text search queries, you must have a text index on your collection. A collection can only have one text search index, but that index can cover multiple fields.

     For example you can run the following in a mongo shell to allow text search over the name and description fields:

    ```console
    db.stores.createIndex( { name: "text", description: "text" } )
    ```

    * ### `$text` Operator
    Use the $text query operator to perform text searches on a collection with a text index.

    $text will `tokenize the search string using whitespace and most punctuation as delimiters`, and perform a logical OR of all such tokens in the search string.

    For example, you could use the following query to find all stores containing any terms from the list “coffee”, “shop”, and “java”:

    ```console
    db.stores.find( { $text: { $search: "java coffee shop" } } )
    ```

* # Aggregation

    Aggregation operations `process data records` and return `computed results`. _Aggregation operations group values from multiple documents together, and can perform a variety of operations on the grouped data to return a single result._

    * ## Aggregation Pipeline
     MongoDB’s aggregation framework is modeled on the concept of `data processing pipelines`. Documents enter a `multi-stage pipeline` that transforms the documents into an aggregated result.

     The most basic pipeline stages provide filters that operate like queries and document transformations that modify the form of the output document.

     Other pipeline operations provide tools for `grouping and sorting documents` by specific field or fields as well as tools for `aggregating the contents of arrays`, including arrays of documents. In addition, pipeline stages can use operators for tasks such as calculating the average or concatenating a string.

    _The pipeline provides efficient data aggregation using native operations within MongoDB, and is the preferred method for data aggregation in MongoDB._

    ![aggregation explaination](https://docs.mongodb.com/manual/_images/aggregation-pipeline.bakedsvg.svg)

    [**Click here to see all the pipeline operators**](https://docs.mongodb.com/manual/reference/operator/aggregation-pipeline/)

* # Replication

    A replica set in MongoDB is a `group of mongod processes that maintain the same data set`. Replica sets provide redundancy and high availability, and are the basis for all production deployments. This section introduces replication in MongoDB as well as the components and architecture of replica sets. The section also provides tutorials for common tasks related to replica sets.

    [Click here to Understand Replication](https://www.youtube.com/watch?v=ShbqrYvs8-w)

