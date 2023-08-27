## Mongo Query Compiler Documentation

### $regexp

Determines if an element satisfies a regular expression.

```javascript
let records = [
  {name: 'Igor'},
  {name: 'Vasiliy'}
];

let query = {name: {$regexp: /iy$/}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Vasiliy'}]
```

Regular expression can also be represented as a string.
`mongo-query-compiler` will automatically convert it to
a regular expression object (RegExp).

```javascript
let query = {name: {$regexp: 'iy$'}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Vasiliy'}]
```

---

[Previous ($mod operator)](./mod.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($regex operator)](./regex.md)
