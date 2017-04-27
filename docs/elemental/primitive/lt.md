## Mongo Query Compiler Documentation

### $lt

Assesses if an object element's value is less than a comparator.

```javascript
let records = [
  {name: 'Bill', age: 30},
  {name: 'Sarah', age: 35},
  {name: 'John', age: 17}
];

let query = compiler({age: {$lt: 18}});
let results = records.filter(query);
//results = [{name: 'John', age: 17}]
```

---

[Previous ($gte operator)](./gte.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next ($lte operator)](./lte.md)
