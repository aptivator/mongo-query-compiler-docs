## Mongo Query Compiler Documentation

### $lte

Tests if an object element's value is less than or equal to a comparator.

```javascript
let records = [
  {name: 'Bill', age: 30},
  {name: 'Sarah', age: 35},
  {name: 'John', age: 17}
];

let query = {age: {$lte: 30}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Bill', age: 30}, {name: 'John', age: 17}]
```

---

[Previous ($lt operator)](./lt.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($in operator)](./in.md)
