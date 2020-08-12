## Mongo Query Compiler Documentation

### $nin

Reverse of the `$in` operator.

```javascript
let records = [
  {name: 'Bill', car: ['toyota', 'jeep']},
  {name: 'Sarah', car: 'lexus'},
  {name: 'John', car: 'volvo'}
];

let query = {car: {$nin: ['toyota', 'lexus', 'jeep']}}
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'John', car: 'volvo'}]
```

---

[Previous ($in operator)](./in.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($all operator)](../array/all.md)
