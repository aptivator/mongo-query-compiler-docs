## Mongo Query Compiler Documentation

### $not

Negates a criterion.  Semantically, `$not` is meant to negate one condition at a 
time.  Specifying multiple criteria is allowed.  In the latter case, `$not` 
behaves as `$nor`.

```javascript
/* $not as a negator of a single condition */

let records = [
  {name: 'Bill', timeSheet: [8, 8.5, 8.1, 8, 8]},
  {name: 'Joane', timeSheet: [7.9, 8, 8, 8.2, 8]},
  {name: 'Stuart', timeSheet: [7.5, 7, 8, 8, 8.2]}
];

let query = {timeSheet: {$not: {$or: {$lte: 7, $gte: 8.5}}}};
let filterer = compiler(query);
let results = records.filter(filterer);
//results = [{name: 'Joane', ... }]
```
```javascript
/* $not as alias for $nor */

let records = [
  {name: 'Bill', timeSheet: [8, 8.5, 8.1, 8, 8]},
  {name: 'Joane', timeSheet: [7.9, 8, 8, 8.2, 8]},
  {name: 'Stuart', timeSheet: [7.5, 7, 8, 8, 8.2]}
];

let query = {timeSheet: {$not: {$lte: 7, $gte: 8.5}}};
let filterer = compiler(query);
let results = records.filter(filterer);
//results = [{name: 'Joane', ... }]
```

---

[Previous ($nor operator)](./nor.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next ($comment operator)](../utility/comment.md)
