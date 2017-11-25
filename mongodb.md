# Mongo

`mongo` - mongod client (epel: `mongodb`)

## database

```mongo
show dbs
use db-name
db.dropDatabase()
```

## collection

```mongo
db.getCollectionNames()
collection = db.getCollection("collection-name")
```

### search

```mongo
collection.find()
collection.find({"attr": "value"})
collection.find({"attr": /^regex$/})
```

### prettyprint

```mongo
collection.find().forEach(printjson)
collection.find().pretty()
```

### delete

```mongo
collection.remove()
collection.remove({"attr": "value"})
collection.remove({"attr": /^regex$/})
```
