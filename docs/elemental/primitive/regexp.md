## Mongo Query Compiler Documentation

### $regexp

Determines if an element fulfills a regular expression.

```javascript
let records = [
  {name: 'Igor'},
  {name: 'Vasiliy'}
];

let query = compiler({name: {$regexp: /iy$/i}});
let results = records.filter(query);
//results = [{name: 'Vasiliy'}]
```

---

[Previous ($mod operator)](./mod.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($type operator)](./type.md)
