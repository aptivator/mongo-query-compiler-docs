## Mongo Query Compiler Documentation

### $elemMatch

Specifies a sub-query on an object's nested array.  `$elemMatch` criteria should 
be specified in exactly the same way as all other queries.  The only exception is 
if an array of primitives is queried.  In the latter case, there is no need to 
provide a path (key) to an object element, because the element is the "object" 
(primitive) itself.  As such, `mongo-query-compiler` can query an array of 
documents (objects) or an array of primitives.  (For more information also see
[Primitives' Filtering](../../primitives-filtering.md)).

```javascript
/* querying an array of primitives */

let scores = [55, 57, 60, 55, 22];

let query = {$gt: 55};
let filterer = compileMongoQuery(query);
let results = scores.filter(filterer);
//results = [57, 60]
```

```javascript
/* $elemMatch on an array of primitives */

let records = [
  {name: 'Bill', timeSheet: [8, 8.5, 8.1, 8, 8]},
  {name: 'Joane', timeSheet: [7.9, 8, 8, 8.2, 10]},
  {name: 'Stuart', timeSheet: [7.5, 7, 8, 8, 8.2]}
];

let query = {timeSheet: {$elemMatch: {$lt: 7.5}}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Stuart', ... }]
```

```javascript
/* $elemMatch on an array of documents */

let records = [{
  name: 'Ivan',
  cars: [
    {brand: 'toyota', model: 'camry', year: 2008},
    {brand: 'nissan', model: 'sentra', year: 2010}
  ]
}, {
  name: 'Charlie',
  cars: [
    {brand: 'acura', model: 'tl', year: 2015}
  ]
}];

let query = {cars: {$elemMatch: {brand: 'toyota'}}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Ivan', ... }]
```

`mongo-query-compiler`, similar to mongodb, allows using sub-object or dot
notations to "see through" the nested array of documents.  The above query may 
be rewritten as illustrated below.  For more complex queries on a nested array 
of documents, `$elemMatch` operator should be used.

```javascript
/* $elemMatch query rewritten using sub-object notation */

let filterer = compileMongoQuery({cars: {brand: 'toyota'}});
```

```javascript
/* $elemMatch query rewritten using dot notation */

let filterer = compileMongoQuery({'cars.brand': 'toyota'});
```

---

[Previous ($size operator)](./size.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($where operator)](../free-form/where.md)
