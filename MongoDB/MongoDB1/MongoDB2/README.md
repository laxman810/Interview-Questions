MONGODB

db to show which db is being used currently.
db.collectionName.drop() to drop that collection in db
db.dropDatabase() will drop the currently using database
MongoDB basically has collection.Each collection has documents in it stored in BSON format
show dbsfor listing all the databases in the db
use nameOfDb to use that db
eg:- use product
now 
db.product.insertOne({key:"value"}) will store document/collection inside the product db
mongodb uses wiredtiger storage engine

CRUD OPERATION

create-insertOne(data,options)insertMany(data,options) 
Read- find(filter,options)findOne(filter,options)
Update-updateOne(filter,data,options)
updateMany(filter,data,options) -- here pass array of multiple docs [{},{},{}]
replaceOne(filter,data,options)
delete-deleteOne(filter,options) deleteMany(filter,options)
//update operation document must contain atomic operation. Hence we use $set 
updateOne({name:"Laxman"},{$set:{marker:"delete"}})
find({distance:{$gt:600}})

UPDATE OPERATION

diffrence between update,updateOne and updateMany
with updateOne and updateMany you have to use $set to make single change
with update you dont have to use $set although it will remove rest of the data and put only the new data
to replace an item you can use 
replaceOne()

when query 
db.collectionName.find().toArray() will fetch all data in the collection
db.collectionName.find().forEach((data)=>{printjson(data)}) // for looping through db

find basically gives you cursor instead of whole data.pretty() can be used only on cursor

UPDATE OPERATION IN MONGODB

reference:https://stackoverflow.com/questions/22071434/mongodb-update-collection-field-if-new-value-is-not-null
using mongod to start the mongodb server
mongod --port 27017 can be used to specify port explicitly
now
mongo -- port 27017 must be specified explicitly to tell mongodb to look in that port

PROJECTION

Projection is a way to get only few data of a document.

db.collectionName.find({},{name:1})  //no filter means fetch all data but...
mentions the key which you want and _id=0 if you dont want _id. Rest of the data are 0 
by default

to use projection in array
db.movies.find({genre:"darama"},{"genres.$:1"})
//here genre is an array [
    "darama",
    "action",
    "thriller"
]

EMBEDDED DOCUMENT

Basically nested document
28 acess structured data.
db.collectionName.find({hobbies:"sports"}).pretty()
//here hobbies is an array.Mongodb is smart enough to find array and look for elements in it

to fetch embedded docs use dot notation
eg: db.collectionName.find({"address.street":"10th"})

DATATYPES IN MONGODB

reference:https://docs.mongodb.com/manual/reference/bson-types/

Number,String,Object,ObjectId,Date(iso),Timestamp

db.collectionName.stats() //shows the  stat of that db

SCHEMA MODELLING

guidelines:
What data does my app need? user info,Product info,Orders(this defines fields)
Where do I need Data?Welcome page,Products page,List Page,Orders Page(deines required collection)
Which kind of data do I need to display?(defines which query you will need)
How often do I fetch data?(Defines weather youll need to optimise for each fetching)

reference vs nested/embedded

reference eg: {                         |   embeded eg:{
    name:"Laxman",                     |   name:"Laxman",
    favBook:2                           |       favBook:{
}                                       |           bookName:"new book"
{                                       |       }
    id:2,                               |   }
    bookName:"new book"                 |
}

when to use?
when there is a one to one relation use embedded.
ie if one person has something unique to him.
When there is one to many relations use reference.
ie if one person likes a book.(many persons can like the same book)
when there is many to many relations use reference.
i.e if one person buys multiple things (shopping)

disadvantage of embeded is there could be repitation of data

$LOOKUP
reference:47

This operator is used to merge related document split up using reference.

you need to use aggregate
//customers
{
    userName:'max',
    favBooks:['id','id2']
}
//books
{
    _id:'id1',
    name:'lord of the rings 1'
}

customers.aggregate([
    {
        $lookup:{
            from:"books",
            localField:"favBooks",
            foreignField:"_id",
            as:"favBookData"
        }
    }
])

MONGODB SERVICE STUFF

59 episode
to run service in background or foreground

CREATE DEEPER

mongodb by default performs Ordered insert.Ordered insert means every insert is processed
standalone,but if one fails,it cancels entire insert operation but it doesnot roll back 
the element it already inserted.

example if I insert a document with id 1 and then insert 3 more document with id 2,1,3 respectively
mongodb insertMany will insert document with id 2 and then stops the process.Thus db now has
document with id 1 and document with id 2. Document with id 3 is not inserted even if its id
is unique.This is default behavior.
You can change this default behavior by passing ordered:false.
now it will insert all the document with unique id except the one that doesnt have unique id
Basically no rollback

WRITECONCERN
//works with insert/update/delete(all write operation)
db.collectionName.insertOne({name:"k",age:2},{writeConcern:{w:0}})
here w is set to 1 by default.If set to 1 you will get acknowledgement
used when you dont mind if few data is not entered in db (faster)
db.collectionName.insertOne({name:"k",age:2},{writeConcern:{w:1,j:1,wtimeout:200}})

j-journal basically is a todo.Its an additional file that keeps the operation that has not been 
completed yet.
if set to true(1) it will acknowledge only when write operation on both journal and disk is
complete.
wtimeout: timeframe you give to complete the write operation before you cancel it.

ATOMICITY

Means either the operation completely fails or completely succeeds.
Mongodb crud operation are Atomic on Document level (including embeded document)
note:-its not atomic for crud multiple like insertMany,updateMany

MONGO IMPORT

you can import data from json file
mongoimport nameOfTheFile.json -d databaseName -c collectionName --jsonArray --drop

-d database name -c collection name
--jsonArray specifies that the json file has more than one collection 
--drop to drop the db if it already exists and rewrite.(else it will append it)

READ DEEPER

to query items in array
name:[
    "abc",
    "xyz",
    "lalala"
]
db.collectionName.find({name:"abc"})
this will return all document which has abc in its array
db.collectionName.find({name:["abc"]})
this will return only those document which has only abc in its array.

OPERATORS
reference:85th episode
$in,$nin,$eq,$ne,$gt,$gte,$lt,$lte

$in
Matches any of the values specified in an array.
price:{$in:[20,14]}
only those documents where price is equal to 20 or 14
$nin is opposite

logical operator
$and,$or,$nor

element operator
$exists,$type
$exists checks to see if the field exists.
reference:87th episode
db.users.find({age:{$exists:true,$ne:null}})
this returns all document that has age field and its value is not null

$type
finds all document that has perticular type of data specified in type docs
{phone:{$type:"number"}} will return only those with type number

EVALUATION

$regex allows you to specify regular expression in query

$expr 
episode 90
can use expression to query documents
eg:{
    _id:1,
    volume:10,
    target:20
},
{
    _id:2,
    volume:20,
    target:19
}
db.movies.find({$expr:{$gt:["$volume","$target"]}})
this returns all the document where volume is greater than target.

ARRAY operator

$all 
Matches arrays that contain all elements specified in the query.
if you want to check if the array has few elements and dont care about
the order use $all
{$all:[{genre:["action","drama"]}]}
//this returns all documents with action and drama in the array genre in any
order

$elemMatch
Selects documents if element in the array field matches all the specified conditions
db.user.find({hobbies:{$elemMatch:{title:"Sports",frequency:{$gte:3}}}})
//this matches document with  exact match of document inside array

UPDATE

use $set to update parts of document
use $inc to increment value

$min

db.user.updateOne({_id:"sdsdsds"},{$min:{age:28}})
If the field does not exists, the $min operator sets the field to the specified value.
If the field exists,and if the value specified is less that existing value then it updates
else it doesnot.

$max opposite of $min

$mul will multiply existing value with the specified value.

$unset operator to remove a field from document

$rename to rename a field in document.

upsert- meaning update or insert
if upsert is set to true,mongodb will find the document and update it.
If not found it will insert the document

episode 111 for update with $elemMatch
episode 112 for updating multiple docs inside array
use .$[] when there is something to update inside embedded document(array multiple ele)
$ sign simply referes to first match
113
$push to push element into array
db.data.updateOne({},{$push:{array:{name:"",age:""}}})
array is the array and we push document into it
use $each if you want to push multiple element into array simultaneously
$sort can be used to sort the array while saving
use $pull to remove element from array
$pop can be used to remove last element in array without criteria

$push: allows duplicate data 
$addToSet: pushes data to array only if its unique

INDEXING

If the data to be returned to almost all of the documents then indexing it
will actually make it slower

db.contacts.createIndex({dob:1})
db.contacts.dropIndex({dob:1})
Indexes are used to speedup query operation.
If indexed it performs index scan instead of full collection scan.

db.contacts.explain().find({})
//here explain gives details of execution

db.contacts.explain("executionStats").find({})
//gives out time of execution and planned followed

COMPOUND INDEX
db.contacts.createIndex({"dob.age:1",gender:1})

_id is indexed by default

unique indexes lets you maintain unique field for a given collection

PARTIAL INDEX

to create index for a filed when you know that only few of its value will
be frequently used
ex: if you are accessing only people of age above 40
db.contacts.createIndex({"dob.age":1},{partialFilterExpression:{gender:"male"}})
//here index is created only for age and person with gender male

If you want to create a unique index where the field in either unique or null
you need to index it with $exists
eg db.users.createIndex({email:1},{unique:true,partialFilterExpression:{email:{$exists:true}}})
//now email is either unique or null

TIME TO LIVE INDEX
used when there is self destroying data like a session

db.session.createIndex({createdAt:1},{expiresAfterSeconds:10})
//can be used only with date and cannot be used as compound index

COVERED QUERY

When docs examined is 0,ie when query gets completed by reading index only
without accessing the documents, it is called covered query. It is the ideal
query and its most efficient.

TEXT INDEX

//language supported
reference:https://docs.mongodb.com/manual/reference/text-search-languages/#text-search-languages
//diffrent language in same index
https://docs.mongodb.com/manual/tutorial/specify-language-for-text-index/#create-a-text-index-for-a-collection-in-multiple-languages

//text:true in mongoose to set text index in mongoose 
//or schema.index({title:"text",description:"text"}) after schema defination
(you can have only one text index per collection)
If you want to search something in a string(description or a paragraph loop)
you can use text index instead of regular index

db.collection.createIndex({description:"text"})
//now mongodb will store all the keywords of the description in array

db.collection.find($text:{$search:"awesome"})//will return document that has awesome
in its description

in order to sort the document fetched using text index you can  use projection
like-
    db.collection.find($text:{$search:"awesome"},{score:{$meta:"textScore"}}).pretty()
//this will give output along with score of the  doc.
    db.collection.find($text:{$search:"awesome"},{score:{$meta:"textScore"}})
    .sort({score:{$meta:"textScore"}}).pretty()
//this will sort output according to textScore

DROPPING TEXT Indexes

db.detail.getIndexes()
//will give back some details along with name of the index
"description_text"
db.detail.dropIndex("description_text")

COMBINED TEXT INDEX

db.detail.createIndex({name:"text",description:"text"})
//this will create a combined index and when searched,it will look in both field.
//text:true in mongoose to set text index in mongoose 
//or schema.index({title:"text",description:"text"}) after schema defination

SEARCH WITHOUT THIS STRING 

db.detail.find({$text:{$search:"nice -new"}})
//this will find a string only if it has nice and doesnt have new

SETTING WEIGHTS FOR COMBINED TEXT INDEX AND DEFAULT LANGUAGE 

db.detail.createIndex({name:"text",description:"text"},{default_language:"spanish",weights:
{name:1,description:10}})
//now default language is spanish instead of english and description has higher weight

//144 bulding indexes

GEOSPATIAL DATA 

longitude first

CREATING DATA

db.places.insertOne({name:"california",location:{type:"Point",coordinates:[-122.343,37.89]})

CREATING GEOSPATIAL INDEX

db.places.createIndex({location:"2dsphere"})

you can find a location near by (location stored in db only),your location being returned
by api, using near operator

FINDING LOCATION NEAR TO A GIVEN COORDINATES

db.places.find({location:{$near:{$geometry:{type:"Point",coordinates:[-122.46,37.767]},
$maxDistance:60,$minDistance:10}}})
//$near is operator for working with geospatial data(it needs geospatial index)
//max and min distance are in meter.If there is any location(from db) 60 meters from
current location(point coordinates),then it would be displayed in the query.

GIVEN AN AREA FIND WHICH POINTS ARE INSIDE IT 

$geoWithin

if type is polygon
db.places.find({location:{$geoWithin:{$geometry:{type:"Polygon",coordinates:[[p1,p2,p3,p4,p1]]}}}})
//here p1,p2.. are array of coordinate eg:p1 = [-122.4567,37.7644]
//this will return all locations(in db) that fall within that polygon

FINDING OUT IF A USER IS INSIDE A SPECIFIC AREA

first save to area in the database
db.areas.insertOne({name:"park",area:{type:"Polygon",coordinate:[[p1,p2,p3,p4,p1]]}})
//this will insert area in the database
//now to check if the given point is inside this area you need to first create index
db.areas.createIndex({area:"2dsphere"})

db.areas.find({area:{$geoIntersects:{$geometry:{type:"Point",coordinate:[-122.232,37,434]}}}})
//this will return a polygon(area) stored in db if the given coordinate is inside it.

//centerSphere takes array as a value-2 coordinates 

WORKING WITH NUMBERICAL DATA

types of number mongodb supports

Integer(int32)  //full number
-2,147,483,648 to 2,147,483,647

Long(int64)  //full number
9,223,372,036,854,775,807 to -9,223,372,036,854,775,807

Double(64bit) //numbers with decimal places default(even if the number is Integer)
decimal values are approximated

High Precision Doubles(128bit)//numbers with decimal places
decimal are stored in high precision(34 decimal digits)

db.science.insertOne({a: 0.3,b:0.1})
db.science.aggregate([$project:{result:{$subtract:[ "$a","$b" ]}}]) //this wont give exact ans

db.science.insertOne{a:NumberDecimal("0.3"),b:NumberDecimal("0.1")}
db.science.aggregate([$project:{result:{$subtract:[ "$a","$b" ]}}]) //this will

By default numbers are stored as float type
ie when you store a number like age:20 it is actually stored as float 20.0000002.
which takes more space

Hence if we use db.num.insertOne({age:NumberInt("29")}) it takes less space

if the number is long(out of range for int32) use int64

db.num.insertOne({valuation:NumberLong("234456733467")})

when storing a number in NumberLong if an operation is performed on it 
say $inc:10
it will convert the number to int32 and hence will store wrong value
Hence if you store it as NumberLong have to operate as NumberLong
$inc:{NumberLong("20")}

MONGODB SECURITY

Authentication and autharization



Transport Encryption
Encryption at Rest

Auditing
Server & Network Config and setup
Backup and Software updates

AGGREGATION FRAMEWORK

Helps retrieve data in the format you need.
Its an alternative to find
$match,$sort,$group,$project //this is the pipeline

simple project
db.science.insertOne({a: 0.3,b:0.1})
db.science.aggregate([$project:{result:{$subtract:[ "$a","$b" ]}}])

$MATCH

reference:https://docs.mongodb.com/manual/reference/operator/aggregation/match/

Filters the document to pass only the documents that match the specified
conditions to the next pipeline.

db.persons.aggregate([{$match:{gender:"female"}}])
//this will return only those documents where the gender is female.

$GROUP

reference:https://docs.mongodb.com/manual/reference/operator/aggregation/group/

Groups document by specific expression and output to the next stage a document
for each distinct grouping.
{ $group: { _id: <expression>, <field1>: { <accumulator1> : <expression1> }, ... } }

db.persons.aggregate([
    {$match:{gender:"female"}},
    {$group:{_id:{}}}
])

163-fullname fetching from firstName and last name and converting it to upper

$push operator helps you to push element into array for every incomming document
//$addToSet if you dont want duplicates

$UNWIND 

helps when you want to pull elements from array first
its opposite of group,while group groups multiple docs into one
unwind takes one doc and makes multiple doc out of it

