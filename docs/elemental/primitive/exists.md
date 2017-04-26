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

The above query `{age: {$exists: true}}` can also be declared by placing 
`$exists` keyword at the top.

```javascript
let query = compiler({$exists: {age: true}});
```

The following query specification may be advantageous if existence is assessed
for more than one object element.  If existence is checked for multiple elements
of a nested object, then `$exists` may be placed "in between" as illustrated
below.

```javascript
let records = [{
  name: 'Elena',
  favorite: {
    food: 'chocolate',
    music: 'trance'
  }
}];

let query = compiler({favorite: {$exists: {food: true, music: true}}});
let results = records.filter(query);
//results = [{name: 'Elena', ... }]
```
The above approach is called query namespacing and may be used with any 
primitive operator (*with some exceptions that will be noted appropriately*).

---

[Previous (Operator Types)](../operator-types.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next ($mod operator)](./mod.md)
