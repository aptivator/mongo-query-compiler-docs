## Mongo Query Compiler Documentation

### $mod

Performs modulo operation on an object element.  The operation's configuration 
is an array consisting of divisor and remainder (in that order).

```javascript
let records = [
  {name: 'Igor', yearBorn: 1960},
  {name: 'Vasiliy', yearBorn: 1981}
];

let query  = compiler({yearBorn: {$mod: [4, 0]}});
let results = records.filter(query);
//results = [{name: 'Igor', yearBorn: 1960}]
```

---

[Previous ($exists operator)](./exists.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next ($regexp operator)](./regexp.md)
