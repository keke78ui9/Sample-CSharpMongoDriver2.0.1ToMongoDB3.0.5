### Sample code - access MongoDB(3.0.5) by using CSharp Mongo Driver(2.0.1)

![](http://res.cloudinary.com/dmwrakaup/image/upload/v1444202927/omlr9bswyenkibxh7ut6.png)

######call local host mongodb
```
            var client = new MongoClient("mongodb://localhost:27017");

            var database = client.GetDatabase("Test");

            var collection = database.GetCollection<BsonDocument>("SampleData");

            var documents = collection.Find(new BsonDocument()).ToListAsync().Result;

            var document = new BsonDocument
            {
                { "name", Guid.NewGuid().ToString() },
                { "age", documents.Count() + 1 }
            };

            collection.InsertOneAsync(document);
```


