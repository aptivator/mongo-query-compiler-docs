## Mongo Query Compiler Documentation

### $in

Evaluates if an object element's value is included in an array of test values.
If an element's value is an array, then `mongo-query-compiler` will determine if 
the array is a subset of the test values.

```javascript
let records = [
  {name: 'Bill', car: ['toyota', 'jeep']},
  {name: 'Sarah', car: 'lexus'},
  {name: 'John', car: 'volvo'}
];

let query = {car: {$in: ['toyota', 'lexus', 'jeep']}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Bill', ... }, {name: 'Sarah', ... }]
```

---

[Previous ($lte operator)](./lte.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($nin operator)](./nin.md)
