## Mongo Query Compiler Documentation

### $eq

Supports all of the implicit equality operations along with deep equality. 
Unlike other primitive operators, $eq does not unwind an object that follows it.
Instead, the object will be used to assess deep equality with queried object's
's value.  (For more information see [Query Namespacing and Unwinding](../../query-namespacing-unwinding.md)).

```javascript
/* deep equality */

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

let query = {favorite: {$eq: {food: 'chocolate'}}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Boris', ... }]
```

---

[Previous (Implicit Equality)](./implicit-eq.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($ne operator)](./ne.md)
