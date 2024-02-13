
# QCM

### Drop index
Data modeling & storage (40 pts)

You have the following documents in a collection:

```javascript
[
  {
    "_id": 5,
    "name": "Stiles",
    "subjects": ["history", "math"]
  },
  {
    "_id": 6,
    "name": "Malia",
    "age": 17,
    "subjects": ["history", "science"],
    "dob": ISODate("2003-09-01")
  },
  {
    "_id": 7,
    "name": "Alisson",
    "age": 21,
    "code": "0092830",
    "dob": ISODate("1999-09-02")
  }
]
```

You notice that the index that was created on the `code` field is no longer needed. When checking for this index, you retrieve the following information:

```javascript
[
  ...,
  {
    "key": {
      "code": 1
    },
    "name": "code_idx",
    "v": 2
  }
]
```

Which queries can you write to remove this index?

```javascript
db.users.dropIndex("code_idx");
```
```javascript
db.users.dropIndexes("code_idx");
```
```javascript
db.users.dropIndex({"code": -1});
```
```javascript
db.users.dropIndexes([{"code": 0}]);
```

### Choice of storage engine
Administration & security (40 pts)

You want to configure a MongoDB cluster in a way that will allow applications to access real-time data changes in a collection. For this to happen, which of the following is a pre-requisite configuration?

- The system must use the WiredTiger storage engine
- The system must use the inMemory storage engine
- The system must use the MMAPv1 storage engine
- The choice of storage engine has no influence here

### Random documents
Data manipulation & queries (40 pts)

Your company wants to implement a lottery system that randomly selects at most 3 users from the `users` collection. 

Which query should you use? 

```javascript
db.users.aggregate({ $sample: { size: 3 } });
```
```javascript
db.users.aggregate({ $random: { size: 3 } });
```
```javascript
db.users.find({ $sample: { size: 3 } });
```
```javascript
db.users.find({ $random: { size: 3 } });
```

### MongoDB latest features
Administration & security (20 pts)

Which of the following features are supported by the latest (v4.4+) MongoDB version?

- Read-only views
- On-demand materialized views
- Joins on collections across different databases
- Custom indexes

### Query with exclusion
Data manipulation & queries (40 pts)

You have the following documents in a collection:

```javascript
[
  {
    "_id": 1,
    "name": "John",
    "age": 27
  },
  {
    "_id": 2,
    "name": "Liam",
    "age": 19
  },
  {
    "_id": 3,
    "name": "Scott",
    "age": 21
  }
]
```

Which queries would exclude the `_id` field from the output?

```javascript
db.collection.find({},
{
  "name": 1,
  "age": 1,
  "_id": 0
});
```
```javascript
db.collection.find({},
{
  "_id": 0
});
```
```javascript
db.collection.find({},
{
  "name": 1,
  "age": 1,
  "_id": -1
})
```
```javascript
db.collection.find({},
{
  "name": 0,
  "age": 0,
  "_id": -1
})
```

### Check if field exists
Data manipulation & queries (40 pts)

You have the following documents in a collection:

```javascript
[
  {
    "_id": 5,
    "name": "Stiles",
    "age": 22
  },
  {
    "_id": 6,
    "name": "Malia",
    "age": 17,
    "dob": ISODate("2003-09-01")
  },
  {
    "_id": 7,
    "name": "Alisson",
    "age": 21,
    "dob": ISODate("1999-09-02")
  },
  {
    "_id": 8,
    "name": "Kira",
    "age": 24,
    "dob": ISODate("1996-08-11")
  }
]
```

You want to return the documents in which the `dob` attribute is defined. Which queries can you use? 

_Select all correct answers._ 

```javascript
db.users.find( { dob: { $exists: true} } );
```
```javascript
db.users.find( { dob: { $ne: null} } );
```
```javascript
db.users.find( { dob: { $exists: 1} } );
```
```javascript
db.users.find( { dob: { $exists: 0} } );
```

### Find query - even value
Data manipulation & queries (40 pts)

You have the following documents in a collection:

```javascript
[
  {
    "_id": 5,
    "name": "Stiles",
    "age": 22
  },
  {
    "_id": 6,
    "name": "Malia",
    "age": 17,
    "dob": ISODate("2003-09-01")
  },
  {
    "_id": 7,
    "name": "Alisson",
    "age": 21,
    "dob": ISODate("1999-09-02")
  },
  {
    "_id": 8,
    "name": "Kira",
    "age": 24,
    "dob": ISODate("1996-08-11")
  }
]
```

You want to find all the documents in which the age of the candidate is an even number. Which query should you use? 

```javascript
db.users.find( { age: { $div: [ 2, 0 ] } } );
```
```javascript
db.users.find( { age: { $mod: [ 2, 0 ] } } );
```
```javascript
db.users.find( { age: { $right: [ 0, 2, 4, 6, 8 ] } } );
```
- You need to write a custom script as there is no appropriate built-in function

### Query with a date range
Data manipulation & queries (20 pts)

You have the following documents in a collection:

```javascript
[
  {
    "_id": 5,
    "name": "Stiles",
    "age": 22
  },
  {
    "_id": 6,
    "name": "Malia",
    "age": 17,
    "dob": ISODate("2003-09-01")
  },
  {
    "_id": 7,
    "name": "Alisson",
    "age": 21,
    "dob": ISODate("1999-09-02")
  },
  {
    "_id": 8,
    "name": "Kira",
    "age": 24,
    "dob": ISODate("1996-08-11")
  }
]
```

You want to retrieve the users for which the date of birth (DOB) falls between two specific dates. Which query should you use?

```javascript
db.users.find({
  dob: {
	$gte: ISODate("2000-08-11"),
	$lte: ISODate("2015-08-11")
  }
});
```
```javascript
db.users.find({
  dob: {
	$after: ISODate("2000-08-11"),
	$before: ISODate("2015-08-11")
  }
});
```
```javascript
db.users.find({
  dob: {
	$between: [
	  ISODate("2000-08-11"), ISODate("2015-08-11")
	  ]
  }
});
```
```javascript
db.users.find({
  dob: {
	$range: [
	  ISODate("2000-08-11"), ISODate("2015-08-11")
	  ]
  }
});
```

### Pagination - Limit
Data manipulation & queries (40 pts)

You store an insurance claims collection with the following schema: 

```javascript
[
    {
        "_id" : "1",
        "person" : "Marow",
        "city" : "Berlin",
        "claim_amount" : 200
    },
    {
        "_id" : "2",
        "person" : "Chris",
        "city" : "New York",
        "claim_amount" : 350
    },
    {
        "_id" : "3",
        "person" : "Zaid",
        "city" : "Berlin",
        "claim_amount" : 195
    },
]
```

This collection has a few thousand claims. You want to fetch only a few results at a time for performance reasons. Which query should you write to fetch the first 20 records of this collection?

- 
```javascript
db.claim.find().offset(20)
```

- 
```javascript
db.claim.find().limit(20)
```

- 
```javascript
db.claim.find().first(20)
```

- 
```javascript
db.claim.find().page(20)
```

### Collection storage
Data modeling & storage (40 pts)

You want to check the storage statistics of the database, including the collection and index sizes (which contains all indexes on the specified collection).

Which command should you use?

- 
```javascript
db.users.aggregate( [ { $collStats: { storageStats: { } } } ] );
```

- 
```javascript
db.users.aggregate( [ { $facets: { storageStats: { } } } ] );
```

- 
```javascript
db.users.find( [ { $collStats: { storageStats: { } } } ] );
```

### Sharding
Data modeling & storage (40 pts)

Which of the following is true regarding sharding in MongoDB?

- Each shard contains a different set of data based on the shard key decided by the user
- Each shard contains a different set of data based on the shard key decided by the system and which cannot be changed
- Each shard node contains an exact copy of the data for redundancy purposes

### Replica sets
Data modeling & storage (40 pts)

Which of the following statement is **false** regarding replica sets in MongoDB?

- They provide data redundancy
- They increase data availability
- They increase the database write performances
- They prevent the existence of a single point of failure in the cluster

# Text

### Index count

You have the following documents in a collection:

```javascript
[
  {
    "_id": 5,
    "name": "Stiles",
    "subjects": ["history", "math"]
  },
  {
    "_id": 6,
    "name": "Malia",
    "age": 17,
    "subjects": ["history", "science"],
    "dob": ISODate("2003-09-01")
  },
  {
    "_id": 7,
    "name": "Alisson",
    "age": 21,
    "code": "0092830",
    "dob": ISODate("1999-09-02")
  }
]
```

Suppose you have created a single index, on the `code` field. How many indexes now exist on this collection? 

_Answer with an integer._

### Create a capped collection

To create a capped collection in MongoDB, we can use the following command:

```bash
db.createCollection("profilelogs", { XXX: true, size: 4096 });
```

What attribute should be written instead of `XXX`?

### cursor.pretty()

Which method should replace `XXX` to display results in a formatted way in the MongoDB shell?

```javascript
> db.games.find({"author": "Coding Escape"}).XXX()
```

```javascript
{
    "_id" : ObjectId("52c542d5449b55922b54ed8d"),
    "title" : "Back to the '80s",
    "authorship" : "Coding Escape"
}
```














# Code
