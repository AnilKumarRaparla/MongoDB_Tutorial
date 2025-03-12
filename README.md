
# MongoDB Tutorial

---

## 1. MongoDB HOME

- **MongoDB** is a **NoSQL database** that stores data in **flexible, JSON-like documents** (BSON format).  
- **No fixed schema**, allowing hierarchical data storage, arrays, and embedded documents.  
- Great for **high volume** and **unstructured data**.

---

## 2. MongoDB Get Started

### Install MongoDB
- Download from [MongoDB Official Website](https://www.mongodb.com/try/download/community).  
- Install MongoDB Compass (GUI) for visual interaction.

### Start MongoDB Server (mongod)
```bash
mongod
```

### Connect to MongoDB Shell (mongosh)
```bash
mongosh
```

---

## 3. MongoDB Query API (Shell/Driver Commands)

MongoDB uses a **rich query language** to interact with the database.

**Basic Syntax**:
```javascript
db.collection_name.find({ key: value });
```

---

## 4. MongoDB Create DB

- To create or switch to a database:
```javascript
use myDatabase;
```

- Show all databases:
```javascript
show dbs;
```

---

## 5. MongoDB Collection

- Collections are **like tables** in RDBMS.

- Create collection:
```javascript
db.createCollection("myCollection");
```

- List collections:
```javascript
show collections;
```

---

## 6. MongoDB Insert

- **Insert One Document**:
```javascript
db.myCollection.insertOne({ name: "John", age: 25 });
```

- **Insert Multiple Documents**:
```javascript
db.myCollection.insertMany([
  { name: "Alice", age: 28 },
  { name: "Bob", age: 30 }
]);
```

---

## 7. MongoDB Find (Read/Query Documents)

- **Find all documents**:
```javascript
db.myCollection.find();
```

- **Find with condition**:
```javascript
db.myCollection.find({ age: { $gt: 25 } });
```

- **Find one document**:
```javascript
db.myCollection.findOne({ name: "John" });
```

---

## 8. MongoDB Update

- **Update one document**:
```javascript
db.myCollection.updateOne(
  { name: "John" },
  { $set: { age: 26 } }
);
```

- **Update multiple documents**:
```javascript
db.myCollection.updateMany(
  { age: { $gt: 25 } },
  { $set: { status: "Active" } }
);
```

---

## 9. MongoDB Delete

- **Delete one document**:
```javascript
db.myCollection.deleteOne({ name: "John" });
```

- **Delete multiple documents**:
```javascript
db.myCollection.deleteMany({ age: { $lt: 30 } });
```

---

## 10. MongoDB Query Operators

| Operator | Description                        | Example                                    |
|---------|------------------------------------|--------------------------------------------|
| `$eq`   | Equal                               | `{ age: { $eq: 25 } }`                     |
| `$gt`   | Greater than                        | `{ age: { $gt: 18 } }`                     |
| `$lt`   | Less than                           | `{ age: { $lt: 30 } }`                     |
| `$in`   | In array                            | `{ name: { $in: ["Alice", "Bob"] } }`      |
| `$and`  | Logical AND                         | `{ $and: [{ age: { $gt: 20 } }, { age: { $lt: 30 } }] }` |

---

## 11. MongoDB Update Operators

| Operator | Description                          | Example                                       |
|----------|--------------------------------------|-----------------------------------------------|
| `$set`   | Set new value                        | `{ $set: { age: 30 } }`                       |
| `$inc`   | Increment value                     | `{ $inc: { age: 1 } }`                        |
| `$unset` | Remove field                         | `{ $unset: { status: "" } }`                  |
| `$push`  | Add value to array                   | `{ $push: { skills: "MongoDB" } }`            |

---

## 12. MongoDB Aggregations

- Aggregation for **complex data analysis** (grouping, filtering, transforming).

**Example**:
```javascript
db.myCollection.aggregate([
  { $match: { age: { $gt: 25 } } },
  { $group: { _id: "$status", total: { $sum: 1 } } }
]);
```

- **Stages**: `$match`, `$group`, `$sort`, `$project`, `$limit`, etc.

---

## 13. MongoDB Indexing/Search

- **Indexing** improves **search performance**.

**Create Index**:
```javascript
db.myCollection.createIndex({ name: 1 }); // Ascending order index
```

- **Find indexes**:
```javascript
db.myCollection.getIndexes();
```

---

## Summary (Key Commands Recap)

| Action                     | Command Example                                  |
|---------------------------|-------------------------------------------------|
| Create DB                  | `use myDatabase`                                 |
| Create Collection          | `db.createCollection("myCollection")`            |
| Insert Document            | `db.myCollection.insertOne({...})`              |
| Find Documents             | `db.myCollection.find()`                        |
| Update Document            | `db.myCollection.updateOne({...}, {...})`      |
| Delete Document            | `db.myCollection.deleteOne({...})`             |
| Aggregation                | `db.myCollection.aggregate([...])`              |
| Create Index               | `db.myCollection.createIndex({ field: 1 })`    |

---

**MongoDB makes working with large and unstructured datasets simple, flexible, and powerful.**

> **Tip:** Use MongoDB Compass for a graphical interface to interact with your databases easily.
