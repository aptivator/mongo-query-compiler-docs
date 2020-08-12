## Mongo Query Compiler Documentation

### $lt

Assesses if an object element's value is less than a comparator.

```javascript
let records = [
  {name: 'Bill', age: 30},
  {name: 'Sarah', age: 35},
  {name: 'John', age: 17}
];

let query = {age: {$lt: 18}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'John', age: 17}]
```

---

[Previous ($gte operator)](./gte.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($lte operator)](./lte.md)
