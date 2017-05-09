## Mongo Query Compiler Documentation

### $where

Allows specification of free-form filtering criteria.  `$where` operator 
receives either a string expression or a full JavaScript function to run against
each document in a collection.

```javascript
/* $where as string expression */

let records = [
  {lastName: 'Johnson', maidenName: null},
  {lastName: 'Jones', maidenName: 'Clarkson'},
  {lastName: 'Smith', maidenName: 'Smith'}
];

let query = compiler({$where: 'this.lastName === this.maidenName'});
let results = records.filter(query);
//results = [{lastName: 'Smith', maidenName: 'Smith'}]
```

**Note:** `this` refers to a current object in the collection.  MongoDB also 
uses `obj` to refer to a document to which a `$where` query is applied.
`mongo-query-compiler` supports only `this` keyword.

```javascript
/* $where as function */

let records = [
  {name: 'Bill', timeSheet: [8, 8.5, 8.1, 8, 8]},
  {name: 'Joane', timeSheet: [7.9, 8, 8, 8.2, 10]},
  {name: 'Stuart', timeSheet: [7.5, 7, 8, 8, 8.2]}
];

let query = compiler({
  $where(o, browser) {
    let {timeSheet} = this;
    let sum = timeSheet.reduce((sum, hours) => sum += hours);
    return sum < 40;
  }
});

let results = records.filter(query);
//results = [{name: 'Stuart', ... }]
```

`$where()` is called with a current document as its context (i.e., `this`). 
Current document and `object-browser` are also given to `$where()` as
parameteres.

**Note:** `$where` operator is top-level and is applied to a document as a whole.

---

[Previous ($elemMatch operator)](../array/elem-match.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($ref operator)](../specialty/ref.md)
