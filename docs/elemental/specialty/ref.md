## Mongo Query Compiler Documentation

### $ref

For all elemental operators (except `$where`), instead of specifying a 
comparator value, a reference may be used, which is a path (address) to one of
the object's elements.  This allows handling of use cases where filtering 
criteria may need to be declared on the object itself.  `$ref` may be used as a 
replacement for a string expression version of `$where`.  **Note:** `$ref` 
operator is not supported by mongodb.

```javascript
/* reference equality */

let records = [
  {lastName: 'Johnson', maidenName: null},
  {lastName: 'Jones', maidenName: 'Clarkson'},
  {lastName: 'Smith', maidenName: 'Smith'}
];

let query = {lastName: {$eq: {$ref: 'maidenName'}}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{lastName: 'Smith', maidenName: 'Smith'}]
```

---

[Previous ($where operator)](../free-form/where.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next (Elemental Operators and Element's Existence)](../element-existence.md)
