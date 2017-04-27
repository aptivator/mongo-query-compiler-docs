## Mongo Query Compiler Documentation

### $all

Assures that object element's array values subsume all the specified values. If
an object element and specified values are not arrays, then they will be 
converted to arrays.

```javascript
let records = [
  {name: 'Bill', car: ['toyota', 'jeep']},
  {name: 'Sarah', car: 'toyota'},
  {name: 'John', car: 'volvo'}
];

let query = compiler({car: {$all: ['toyota']}});
let results = records.filter(query);
//results = [{name: 'Bill', ... }, {name: 'Sarah', ... }]
```

---

[Previous ($nin operator)](../primitive/nin.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($size operator)](./size.md)
