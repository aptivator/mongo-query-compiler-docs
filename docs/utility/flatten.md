## Mongo Query Compiler Documentation

### $flatten

Directs `object-browser` to flatten nested multidimensional arrays.  Flattening
allows accessing objects nested in an array as if the objects were not nested.
`$flatten` can be declared anywhere in the query.  It is recommended that the
operator is set closest to the elemental operator that needs the flattened array.
`$flatten` can also be applied to the referenced access path.  In that case,
`$flatten` should be placed parallel to the `$ref` operator.

```javascript
/* sample data */

let records = [{ 
  item: 23432123,
  reservedFor: 'John',
  store: [{
    number: '222', 
    qty: 51,
    region: 'NE',
    employees: [{
      name: {
        first: 'John',
        last: 'Doe'
      },
      age: 22
    }, {
      name: {
        first: 'Jack',
        last: 'Smith'
      },
      age: 27
    }]
  }, { 
    number: '212', 
    qty: 11,
    employees: [{
      name: {
        first: 'Kate',
        last: 'Jones'
      }
    }]
  }] 
}];
```

#### `$flatten`ing in regular access

```javascript
/* accessing without $flatten */

let query = {'store.employees.name.first': 'John'};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = []
```

`store.employees` is an array of arrays of employee name objects and going
beyond `store.employees` using dot notation will not access any of the nested
objects' elements.  The solution is to flatten the multidimensional array.

```javascript
/* accessing WITH $flatten */

let query = {'store.employees.name.first': {$eq: 'John', $flatten: true}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{item: 23432123, ... }]
```

As noted in the introduction, `$flatten` can be placed anywhere in a query.

```javascript
/* accessing WITH $flatten placed at the top of the query */

let query = {
  $flatten: true,
  store: {
    employess: {
      name: {
        first: {
          $eq: 'John'
        }
      }
    }
  }
};

let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{item: 23432123, ... }]
```

A more complex flattening can be devised by overriding `$flatten`s declared 
near the top of the query with `$flatten`s set inwardly.

```javascript
/* overriding top-most $flatten */

let query = {
  $flatten: true,
  store: {
    employess: {
      name: {
        first: {
          $flatten: false
          $eq: 'John'
        }
      }
    }
  }
};

let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = []
```

The recommended best practice is to place `$flatten` very near the last property
name needed for an element's access.

#### `$flatten` in `$ref` declarations

In reference settings, `$flatten` should be specified parallel to the `$ref`
operator.

```javascript
let query = {
  reservedFor: {
    $in: {
      $ref: 'store.employees.name.first', 
      $flatten: true
    }
  }
};

let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{item: 23432123, ... }]
```

---

[Previous ($comment operator)](./comment.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next (Query Namespacing and Unwinding)](../query-namespacing-unwinding.md)
