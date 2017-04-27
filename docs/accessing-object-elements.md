## Mongo Query Compiler Documentation

### Accessing Object Elements

`mongo-query-compiler` uses [object-browser](https://github.com/aptivator/object-browser)
to access object elements.  The compiler itself supports three schemes for
specifying a path to an object's element: dot, sub-object, and mixed notations.

```javascript
/* sample data */

let records = [{
  name: 'Dmitriy',
  hobbies: [{
    hobby: 'yoga',
    tags: ['fitness', 'yoga', 'exercise']
  }, {
    hobby: 'writing',
    tags: ['technical', 'composition']
  }]
}, {
  name: 'Sue',
  hobbies: [{
    hobby: 'cooking',
    tags: ['nutrition', 'recipes']
  }]
}];
```
```javascript
/* access via dot notation */

let query = {
  'hobbies.0.tags': {
    //filtering criteria specification  
  }
};
```
```javascript
/* access via sub-object notation */

let query = {
  hobbies: {
    0: {
      tags: {
        //filtering criteria specification
      }
    }
  }
};
```
```javascript
/* access via mixed notation */

let query = {
  'hobbies.0': {
    tags: {
      //filtering criteria specification
    }
  }
};
```

Whichever scheme is the most appropriate depends on the data queried.  Operators'
documentation and [Query Namespacing and Unwinding](./query-namespacing-unwinding.md) 
provide the necessary examples to get started.

---

[Previous (Operator Types)](./operator-types.md) :snowflake: 
[Table of Contents](../README.md) :snowflake: 
[Next ($exists operator)](./elemental/primitive/exists.md)
