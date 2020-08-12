## Mongo Query Compiler Documentation

### $gte

Determines if an object element's value is greater than or equal to a comparator.

```javascript
let records = [
  {name: 'Bill', age: 30},
  {name: 'Sarah', age: 35},
  {name: 'John', age: 17}
];

let query = compileMongoQuery({age: {$gte: 30}});
let results = records.filter(query);
//results = [{name: 'Bill', age: 30}, {name: 'Sarah', age: 35}]
```

---

[Previous ($gt operator)](./gt.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($lt operator)](./lt.md)
