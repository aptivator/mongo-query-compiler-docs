## Mongo Query Compiler Documentation

### $gte

Determines if an object element's value is greater than or equal to a comparator.

```javascript
let records = [
  {name: 'Bill', age: 30},
  {name: 'Sarah', age: 35},
  {name: 'John', age: 17}
];

let query = {age: {$gte: 30}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Bill', age: 30}, {name: 'Sarah', age: 35}]
```

---

[Previous ($gt operator)](./gt.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($lt operator)](./lt.md)
