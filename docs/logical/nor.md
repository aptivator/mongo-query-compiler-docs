## Mongo Query Compiler Documentation

### $nor

Asserts that all of the specified criteria do not apply to a document.

```javascript
let records = [
  {name: 'Bill', timeSheet: [8, 8.5, 8.1, 8, 8]},
  {name: 'Joane', timeSheet: [7.9, 8, 8, 8.2, 8]},
  {name: 'Stuart', timeSheet: [7.5, 7, 8, 8, 8.2]}
];

let query = {timeSheet: {$nor: {$lte: 7, $gte: 8.5}}};
let filterer = compiler(query);
let results = records.filter(filterer);
//results = [{name: 'Joane', ... }]
```

---

[Previous ($or operator)](./or.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next ($not operator)](./not.md)
