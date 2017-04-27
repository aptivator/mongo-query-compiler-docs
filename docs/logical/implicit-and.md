## Mongo Query Compiler Documentation

### Implicit $and

Asserts whether multiple conditions are all satisfied.  A fundamental way to 
specify multiple criteria is to list them in the same query.

```javascript
let records = [{
  name: 'Elena',
  favorite: {
    food: 'chocolate',
    music: 'trance'
  }
}, {
  name: 'Boris',
  favorite: {
    food: 'chocolate'
  }
}];

let query = compiler({favorite: {food: /^cho/, music: {$exists: false}}});
let results = records.filter(query);
//results = [{name: 'Boris', ... }]
```

---

[Previous ($where operator)](../elemental/free-form/where.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next ($and operator)](./and.md)
