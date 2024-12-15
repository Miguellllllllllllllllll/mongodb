# Mongosh

### start + enter db:

```
show dbs
```

```
use (dbname)
```

```
show collections
```

### clean screen:

```
cls
```

### adding smt new into a collection:

```
db.(collectionname).insertOne({ smt: "Stringtype", int: 20, array: ["stingtype", "stringtype"] })
```

### adding more then 1 thing:

```
db.(collectionname).insertMany([

{ smt: "Stringtype", int: 20, array: ["stingtype", "stringtype"] }
,
{ smt: "Stringtype", int: 20, array:["stingtype", "stringtype"] }

])
```

**if the collection doesnt exist, just write it, mongodb will auto-create it**

### list all docs:

```
db.(collectionname).find()
```

**Copy the ObjectId**

### Deleting docs from collection by id

```
db.(collectionname).deleteOne({ _id: ObjectId("298893893893") })
```

### Deleting multiple docs from collection by smt else:

```
db.(collectionname).deleteMany({ author: "Jamal" })
```

### Updating docs from collection by id

**first where, and then what**

```
db.(collectionname).updateOne({ _id: ObjectId("298893893893")}, {$set: { rating: 7, pages: 360 } } )
```

### Updating multiple docs from collection by id

```
db.(collectionname).updateMany({ author: "James" }, {$set: {author: "James bond"}})
```

### Updating a number in docs from collection by id

```
db.(collectionname).updateOne({ _id: ObjectId("298893893893")}, {$inc: { rating: 1} } )
```

**minus numberss work here too!**

### remove or add smt in an array in docs from collection by id

**remove**

```
db.(collectionname).updateOne({ _id: ObjectId("298893893893")}, {$pull: { genres: "fantasy"} } )
```

**added**

```
db.(collectionname).updateOne({ _id: ObjectId("298893893893")}, {$push: { genres: "fantasy"} } )
```

**multiple**

```
db.(collectionname).updateOne({ _id: ObjectId("298893893893")}, {$push: {genres: {$each: ["1","2"] } } } )
```
