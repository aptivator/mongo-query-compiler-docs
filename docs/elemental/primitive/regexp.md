## Mongo Query Compiler Documentation

### $regexp

Determines if an element fulfills a regular expression.

```javascript
let records = [
  {name: 'Igor'},
  {name: 'Vasiliy'}
];

let query = {name: {$regexp: /iy$/i}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Vasiliy'}]
```

---

[Previous ($mod operator)](./mod.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($type operator)](./type.md)
