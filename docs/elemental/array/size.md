## Mongo Query Compiler Documentation

### $size

Tests if an object element's array is of a certain size.

```javascript
let records = [
  {name: 'Bill', car: ['toyota', 'jeep']},
  {name: 'Sarah', car: 'toyota'},
  {name: 'John', car: 'volvo'}
];

let query = compiler({car: {$size: 2}});
let results = records.filter(query);
//results = [{name: 'Bill', car: ['toyota', 'jeep']}]
```

---

[Previous ($all operator)](./all.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next ($elemMatch operator)](./elem-match.md)
