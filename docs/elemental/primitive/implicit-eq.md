## Mongo Query Compiler Documentation

### Implicit Equality

Determines equality of an object element against a primitive value, a regular
expression, or an array.  To test object element's (deep) equality against some 
object, use `$eq` operator.

```javascript
let records = [{
  name: 'Elena',
  favorite: {
    food: 'chocolate',
    music: 'trance',
    books: ['Dune', 'Fountainhead']
  }
}];

let query = {name: 'Elena'};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Elena', ... }]
```

To test equality of a nested element, specify access to it using a sub-object
or dot notation.

```javascript
/* sub-object notation */

let query = {favorite: {food: /^cho/}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Elena', ... }]
```

```javascript
/* dot notation */

let query = {'favorite.music': 'trance'};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Elena', ... }]
```

If an object element is an array, then equality is asserted if a comparison 
value equals to the array or a comparison value equals to one of the array's 
values.

```javascript
/* array to array equality */

let query = {'favorite.books': ['Dune', 'Fountainhead']};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Elena', ... }]
```

```javascript
/* array to value equality */

let query = {'favorite.books': 'Dune'};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Elena', ... }]
```

---

[Previous ($type operator)](./type.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($eq operator)](./eq.md)
