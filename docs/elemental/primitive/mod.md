## Mongo Query Compiler Documentation

### $mod

Performs modulo operation on an object element's value.  The operation's 
configuration is an array consisting of a divisor and remainder, respectively.

```javascript
let records = [
  {name: 'Igor', yearBorn: 1960},
  {name: 'Vasiliy', yearBorn: 1981}
];

let query = {yearBorn: {$mod: [4, 0]}};
let filterer  = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Igor', yearBorn: 1960}]
```

---

[Previous ($exists operator)](./exists.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($regexp operator)](./regexp.md)
