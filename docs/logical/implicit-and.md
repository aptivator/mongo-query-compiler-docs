## Mongo Query Compiler Documentation

### Implicit $and

Asserts whether multiple conditions are satisfied.  A fundamental way to list 
several criteria is to place them in the same query.

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

let query = {favorite: {food: /^cho/, music: {$exists: false}}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Boris', ... }]
```

---

[Previous (Elemental Operators and Element's Existence)](../elemental/element-existence.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next ($and operator)](./and.md)
