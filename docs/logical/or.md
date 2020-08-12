## Mongo Query Compiler Documentation

### $or

Tests if at least one criteria is met.  Like `$and`, `$or` query can be
specified as an object or an array of queries.

```javascript
let records = [
  {name: 'Bill', timeSheet: [8, 8.5, 8.1, 8, 8]},
  {name: 'Joane', timeSheet: [7.9, 8, 8, 8.2, 8]},
  {name: 'Stuart', timeSheet: [7.5, 7, 8, 8, 8.2]}
];

let query = {timeSheet: {$or: {$lte: 7, $gte: 8.5}}};
let filterer = compiler(query);
let results = records.filter(filterer);
//results = [{name: 'Bill', ... }, {name: 'Stuart', ... }]
```

---

[Previous ($and operator)](./and.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next ($nor operator)](./nor.md)
