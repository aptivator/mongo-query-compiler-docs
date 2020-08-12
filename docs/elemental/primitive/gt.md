## Mongo Query Compiler Documentation

### $gt

Diagnoses if an object element's value is greater than a comparator.  **Note:**
for all comparison operators ($gt, $gte, $lt, $lte), an object element's value
can be an array.  A search criterion will be deemed satisfied if one of the 
array's values matches a comparison.

```javascript
/* comparison against a primitive object element's value */

let records = [
  {name: 'Bill', age: 30},
  {name: 'Sarah', age: 35},
  {name: 'John', age: 17}
];

let query = {age: {$gt: 30}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Sarah', age: 35}]
```
```javascript
/* comparison against an array object element's value */ 

let records = [
  {name: 'Bill', timeSheet: [8, 8.5, 8.1, 8, 8]},
  {name: 'Joane', timeSheet: [7.9, 8, 8, 8.2, 10]},
  {name: 'Stuart', timeSheet: [7.5, 7, 8, 8, 8.2]}
];

let query = {timeSheet: {$gt: 9.9}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Joane', ... }]
```

---

[Previous ($eq operator)](./eq.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($gte operator)](./gte.md)
