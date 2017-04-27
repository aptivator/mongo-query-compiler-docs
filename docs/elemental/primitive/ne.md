## Mongo Query Compiler Documentation

### $ne

Checks for inequality and is the reverse of `$eq` operator.

```javascript
let records = [
  {lastName: 'Johnson', maidenName: null},
  {lastName: 'Jones', maidenName: 'Clarkson'},
  {lastName: 'Smith', maidenName: 'Smith'}
];

let query = compiler({lastName: {$ne: 'Johnson'}});
let results = records.filter(query);
//results = [{lastName: 'Jones', ... }, {lastName: 'Smith', ... }]
```

---

[Previous ($eq operator)](./eq.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($gt operator)](./gt.md)
