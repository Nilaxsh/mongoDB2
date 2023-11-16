**1. Create a Database called customers?**
```
use cutomers
switched to db customers
```
**2.Create a collection called customerdetails?**
```
 db.createCollection("customerdetails")
{ ok: 1 }
```
**3.Insert all documents into the collection named   customerdetails?**
```
 db.customerdetails.insertMany([{"name":"john","age":25,"gender":"male","city":"Newyork"},{"name":"Emily","age":22,"gender":"female","city":"London"},{"name":"daniel","age":28,"gender":"male","city":"sydney"},{"name":"sophia","age":24,"gender":"female","city":"paris"},{"name":"william","age":26,"gender":"male","city":"chicago"},{"name":"olivia","age":23,"gender":"female","city":"los Angeles"},{"name":"Benjamin","age":27,"gender":"male","city":"toronto"},{"name":"mila","age":29,"gender":"female","city":"Berlin"},{"name":"james","age":30,"gender":"male","city":"Tokyo"}])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("6555a4de463de7194d63715f"),
    '1': ObjectId("6555a4de463de7194d637160"),
    '2': ObjectId("6555a4de463de7194d637161"),
    '3': ObjectId("6555a4de463de7194d637162"),
    '4': ObjectId("6555a4de463de7194d637163"),
    '5': ObjectId("6555a4de463de7194d637164"),
    '6': ObjectId("6555a4de463de7194d637165"),
    '7': ObjectId("6555a4de463de7194d637166"),
    '8': ObjectId("6555a4de463de7194d637167")
  }
}
```
 **4.Retrieve all documents from the collection and sort the results by the “age” field    in ascending order?**
 ```
db.customerdetails.find().sort({age:1}).pretty()
[
  {
    _id: ObjectId("6555a26d463de7194d63715b"),
    name: 'Emily',
    age: 22,
    gender: 'female',
    city: 'London'
  },
  {
    _id: ObjectId("6555a4de463de7194d637160"),
    name: 'Emily',
    age: 22,
    gender: 'female',
    city: 'London'
  },
  {
    _id: ObjectId("6555a4de463de7194d637164"),
    name: 'olivia',
    age: 23,
    gender: 'female',
    city: 'los Angeles'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715d"),
    name: 'sophia',
    age: 24,
    gender: 'female',
    city: 'paris'
  },
  {
    _id: ObjectId("6555a4de463de7194d637162"),
    name: 'sophia',
    age: 24,
    gender: 'female',
    city: 'paris'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715a"),
    name: 'john',
    age: 25,
    gender: 'male',
    city: 'Newyork'
  },
  {
    _id: ObjectId("6555a4de463de7194d63715f"),
    name: 'john',
    age: 25,
    gender: 'male',
    city: 'Newyork'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715e"),
    name: 'william',
    age: 26,
    gender: 'male',
    city: 'chicago'
  },
  {
    _id: ObjectId("6555a4de463de7194d637163"),
    name: 'william',
    age: 26,
    gender: 'male',
    city: 'chicago'
  },
  {
    _id: ObjectId("6555a4de463de7194d637165"),
    name: 'Benjamin',
    age: 27,
    gender: 'male',
    city: 'toronto'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715c"),
    name: 'daniel',
    age: 28,
    gender: 'male',
    city: 'sydney'
  },
  {
    _id: ObjectId("6555a4de463de7194d637161"),
    name: 'daniel',
    age: 28,
    gender: 'male',
    city: 'sydney'
  },
  {
    _id: ObjectId("6555a4de463de7194d637166"),
    name: 'mila',
    age: 29,
    gender: 'female',
    city: 'Berlin'
  },
  {
    _id: ObjectId("6555a4de463de7194d637167"),
    name: 'james',
    age: 30,
    gender: 'male',
    city: 'Tokyo'
  }
]
```
**5. Count the number of females?**
```
 db.customerdetails.countDocuments({"gender":"female"})
6
```
**6.Insert one document into the customerdetails collection?**
```
 db.customerdetails.insertOne({"name":"thaksha","age":29,"gender":"female","city":"ontario"})
{
  acknowledged: true,
  insertedId: ObjectId("6555a952463de7194d637168")
}
db.customerdetails.find()
[
  {
    _id: ObjectId("6555a26d463de7194d63715a"),
    name: 'john',
    age: 25,
    gender: 'male',
    city: 'Newyork'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715b"),
    name: 'Emily',
    age: 22,
    gender: 'female',
    city: 'London'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715c"),
    name: 'daniel',
    age: 28,
    gender: 'male',
    city: 'sydney'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715d"),
    name: 'sophia',
    age: 24,
    gender: 'female',
    city: 'paris'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715e"),
    name: 'william',
    age: 26,
    gender: 'male',
    city: 'chicago'
  },
  {
    _id: ObjectId("6555a4de463de7194d63715f"),
    name: 'john',
    age: 25,
    gender: 'male',
    city: 'Newyork'
  },
  {
    _id: ObjectId("6555a4de463de7194d637160"),
    name: 'Emily',
    age: 22,
    gender: 'female',
    city: 'London'
  },
  {
    _id: ObjectId("6555a4de463de7194d637161"),
    name: 'daniel',
    age: 28,
    gender: 'male',
    city: 'sydney'
  },
  {
    _id: ObjectId("6555a4de463de7194d637162"),
    name: 'sophia',
    age: 24,
    gender: 'female',
    city: 'paris'
  },
  {
    _id: ObjectId("6555a4de463de7194d637163"),
    name: 'william',
    age: 26,
    gender: 'male',
    city: 'chicago'
  },
  {
    _id: ObjectId("6555a4de463de7194d637164"),
    name: 'olivia',
    age: 23,
    gender: 'female',
    city: 'los Angeles'
  },
  {
    _id: ObjectId("6555a4de463de7194d637165"),
    name: 'Benjamin',
    age: 27,
    gender: 'male',
    city: 'toronto'
  },
  {
    _id: ObjectId("6555a4de463de7194d637166"),
    name: 'mila',
    age: 29,
    gender: 'female',
    city: 'Berlin'
  },
  {
    _id: ObjectId("6555a4de463de7194d637167"),
    name: 'james',
    age: 30,
    gender: 'male',
    city: 'Tokyo'
  },
  {
    _id: ObjectId("6555a952463de7194d637168"),
    name: 'thaksha',
    age: 29,
    gender: 'female',
    city: 'ontario'
  }
]
```
**7. Update city=SriLanka to John?**
```
 db.customerdetails.update({"name":"john","age":25,"gender":"male"},{$set:{"city":"jaffna"}},{"upsert":"true"})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
```
**8. Remove the customer from Tokyo?**
```
db.customerdetails.remove({"city":"Tokyo"})
DeprecationWarning: Collection.remove() is deprecated. Use deleteOne, deleteMany, findOneAndDelete, or bulkWrite.
{ acknowledged: true, deletedCount: 1 }
```
**9. Find customers not from Los Angeles.**
```
db.customerdetails.find({"city":{$ne:"los Angeles"}})
[
  {
    _id: ObjectId("6555a26d463de7194d63715a"),
    name: 'john',
    age: 25,
    gender: 'male',
    city: 'jaffna'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715b"),
    name: 'Emily',
    age: 22,
    gender: 'female',
    city: 'London'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715c"),
    name: 'daniel',
    age: 28,
    gender: 'male',
    city: 'sydney'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715d"),
    name: 'sophia',
    age: 24,
    gender: 'female',
    city: 'paris'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715e"),
    name: 'william',
    age: 26,
    gender: 'male',
    city: 'chicago'
  },
  {
    _id: ObjectId("6555a4de463de7194d63715f"),
    name: 'john',
    age: 25,
    gender: 'male',
    city: 'Newyork'
  },
  {
    _id: ObjectId("6555a4de463de7194d637160"),
    name: 'Emily',
    age: 22,
    gender: 'female',
    city: 'London'
  },
  {
    _id: ObjectId("6555a4de463de7194d637161"),
    name: 'daniel',
    age: 28,
    gender: 'male',
    city: 'sydney'
  },
  {
    _id: ObjectId("6555a4de463de7194d637162"),
    name: 'sophia',
    age: 24,
    gender: 'female',
    city: 'paris'
  },
  {
    _id: ObjectId("6555a4de463de7194d637163"),
    name: 'william',
    age: 26,
    gender: 'male',
    city: 'chicago'
  },
  {
    _id: ObjectId("6555a4de463de7194d637165"),
    name: 'Benjamin',
    age: 27,
    gender: 'male',
    city: 'toronto'
  },
  {
    _id: ObjectId("6555a4de463de7194d637166"),
    name: 'mila',
    age: 29,
    gender: 'female',
    city: 'Berlin'
  },
  {
    _id: ObjectId("6555a952463de7194d637168"),
    name: 'thaksha',
    age: 29,
    gender: 'female',
    city: 'ontario'
  }
]
cutomers> db.customerdetails.find({"age":{$gt:("25")}})

cutomers> db.customerdetails.find({"age":{$gt:("25")}})

cutomers> db.customerdetails.find({"age":{$gt:(25)}})
[
  {
    _id: ObjectId("6555a26d463de7194d63715c"),
    name: 'daniel',
    age: 28,
    gender: 'male',
    city: 'sydney'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715e"),
    name: 'william',
    age: 26,
    gender: 'male',
    city: 'chicago'
  },
  {
    _id: ObjectId("6555a4de463de7194d637161"),
    name: 'daniel',
    age: 28,
    gender: 'male',
    city: 'sydney'
  },
  {
    _id: ObjectId("6555a4de463de7194d637163"),
    name: 'william',
    age: 26,
    gender: 'male',
    city: 'chicago'
  },
  {
    _id: ObjectId("6555a4de463de7194d637165"),
    name: 'Benjamin',
    age: 27,
    gender: 'male',
    city: 'toronto'
  },
  {
    _id: ObjectId("6555a4de463de7194d637166"),
    name: 'mila',
    age: 29,
    gender: 'female',
    city: 'Berlin'
  },
  {
    _id: ObjectId("6555a952463de7194d637168"),
    name: 'thaksha',
    age: 29,
    gender: 'female',
    city: 'ontario'
  }
]
cutomers> db.customerdetails.find({"age":{$lt:(25)},"gender":"male"})cutomers> db.customerdetails.find({"age":{$lt:(26)},"gender":"male"}) 
[
  {
    _id: ObjectId("6555a26d463de7194d63715a"),
    name: 'john',
    age: 25,
    gender: 'male',
    city: 'jaffna'
  },
  {
    _id: ObjectId("6555a4de463de7194d63715f"),
    name: 'john',
    age: 25,
    gender: 'male',
    city: 'Newyork'
  }
]
```
**10.Find the customers who are older than age 25?**
```
db.customerdetails.find({"age":{$gt:(25)}})
[
  {
    _id: ObjectId("6555a26d463de7194d63715c"),
    name: 'daniel',
    age: 28,
    gender: 'male',
    city: 'sydney'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715e"),
    name: 'william',
    age: 26,
    gender: 'male',
    city: 'chicago'
  },
  {
    _id: ObjectId("6555a4de463de7194d637161"),
    name: 'daniel',
    age: 28,
    gender: 'male',
    city: 'sydney'
  },
  {
    _id: ObjectId("6555a4de463de7194d637163"),
    name: 'william',
    age: 26,
    gender: 'male',
    city: 'chicago'
  },
  {
    _id: ObjectId("6555a4de463de7194d637165"),
    name: 'Benjamin',
    age: 27,
    gender: 'male',
    city: 'toronto'
  },
  {
    _id: ObjectId("6555a4de463de7194d637166"),
    name: 'mila',
    age: 29,
    gender: 'female',
    city: 'Berlin'
  },
  {
    _id: ObjectId("6555a952463de7194d637168"),
    name: 'thaksha',
    age: 29,
    gender: 'female',
    city: 'ontario'
  }
]
```
**11.Retrieve the males who are less than 25?**
```
db.customerdetails.find({"age":{$lt:(26)},"gender":"male"}) 
[
  {
    _id: ObjectId("6555a26d463de7194d63715a"),
    name: 'john',
    age: 25,
    gender: 'male',
    city: 'jaffna'
  },
  {
    _id: ObjectId("6555a4de463de7194d63715f"),
    name: 'john',
    age: 25,
    gender: 'male',
    city: 'Newyork'
  }
]
```
**12.Update Francis age to 35, if Francis is not available upsert.**
```
 db.customerdetails.update({"name":"francis"},{$set:{"age":35}},{"upsert":"true"})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 0,
  modifiedCount: 0,
  upsertedCount: 0
}
```
**13.Retrieve males who are younger than 30 and older than25?**
```
db.customerdetails.find({"age":{$lt:(30),$gt:(25)},"gender":"male"})
[
  {
    _id: ObjectId("6555a26d463de7194d63715c"),
    name: 'daniel',
    age: 28,
    gender: 'male',
    city: 'sydney'
  },
  {
    _id: ObjectId("6555a26d463de7194d63715e"),
    name: 'william',
    age: 26,
    gender: 'male',
    city: 'chicago'
  },
  {
    _id: ObjectId("6555a4de463de7194d637161"),
    name: 'daniel',
    age: 28,
    gender: 'male',
    city: 'sydney'
  },
  {
    _id: ObjectId("6555a4de463de7194d637163"),
    name: 'william',
    age: 26,
    gender: 'male',
    city: 'chicago'
  },
  {
    _id: ObjectId("6555a4de463de7194d637165"),
    name: 'Benjamin',
    age: 27,
    gender: 'male',
    city: 'toronto'
  }
]
```
**14.Find a customer who is lesser than or equal to 23?**
```
db.customerdetails.find({"age":{$lte:(23)}})
[
  {
    _id: ObjectId("6555a26d463de7194d63715b"),
    name: 'Emily',
    age: 22,
    gender: 'female',
    city: 'London'
  },
  {
    _id: ObjectId("6555a4de463de7194d637160"),
    name: 'Emily',
    age: 22,
    gender: 'female',
    city: 'London'
  },
  {
    _id: ObjectId("6555a4de463de7194d637164"),
    name: 'olivia',
    age: 23,
    gender: 'female',
    city: 'los Angeles'
  }
]
```

























