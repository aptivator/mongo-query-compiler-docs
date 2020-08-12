## Mongo Query Compiler Documentation

### $exists

Assesses existence of an object element.  **Note:** object element existence is 
tested by checking if object keys include the assessed element's name.

```javascript
import {compileMongoQuery} from 'mongo-query-compiler';

let records = [
  {name: 'Dmitriy', age: 123},
  {name: 'Ivan', age: undefined},
  {name: 'Olga'}
];

let query = {age: {$exists: true}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Dmitriy', age: 123}, {name: 'Ivan', age: undefined}]
```

---

[Previous (Accessing Object Elements)](../../accessing-object-elements.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($mod operator)](./mod.md)
