## Mongo Query Compiler Documentation

### $type

Checks if an assessed element is of a certain type.  `mongo-query-compiler` uses 
`lodash`'s `is` family of functions to determine types.  To specify a type 
simply list a name of one of the `is` functions without the `is`.  For example, 
`lodash` has `isNumber`, `isInteger`, and `isString` methods.  The types that 
these represent are `number`, `integer`, and `string`, respectively.

```javascript
let records = [
  {name: 'Vladimir', age: 55, married: true},
  {name: 'Natalya', age: 45, married: 'no'}
];

let query = {married: {$type: 'boolean'}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Vladimir', age: 55, married: true}]
```

---

[Previous ($regexp operator)](./regexp.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next (Implicit Equality)](./implicit-eq.md)
