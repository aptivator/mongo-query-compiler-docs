## Mongo Query Compiler Documentation

### $exists

Assesses existence of an object element.  **Note:** object element existence is 
tested by checking if object keys include the assessed element's name.

```javascript
import compiler from 'mongo-query-compiler';

let records = [
  {name: 'Dmitriy', age: 123},
  {name: 'Ivan', age: undefined},
  {name: 'Olga'}
];

let query = compiler({age: {$exists: true}});
let results = records.filter(query);
//results = [{name: 'Dmitriy', age: 123}, {name: 'Ivan', age: undefined}]
```

---

[Previous (Accessing Object Elements)](../../accessing-object-elements.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($mod operator)](./mod.md)
