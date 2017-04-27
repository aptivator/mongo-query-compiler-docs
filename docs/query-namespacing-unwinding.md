## Mongo Query Compiler Documentation

### Query Namespacing and Unwinding

Consider the following documents array:

```javascript
let records = [{
  name: 'Elena',
  favorites: {
    food: 'chocolate',
    music: 'trance'
  }
}, {
  name: 'Irina',
  favorites: {
    food: 'blini'
  }
}];
```

Suppose a subset has to be filtered consisting of documents that have existing 
`food` and `music` in `favorites`.  Here's one such query:

```javascript
let query = compiler({
  'favorites.food': {$exists: true}, 
  'favorites.music': {$exists: true}
});

let results = records.filter(query);
//results = [{name: 'Elena', ... }]
```

#### Query Namespacing

The query seems more verbose than necessary and can be simplified by using
`favorites` as a namespace to access its `food` and `music` properties:

```javascript
let query = compiler({
  favorites: {
    food: {$exists: true},
    music: {$exists: true}
  }
});

let results = records.filter(query);
//results = [{name: 'Elena', ... }]
```

#### Query Unwinding

The last query can be simplified further by "giving" `exists` operator an object
of property names whose existence is to be ascertained.  When `$exists` receives
an object, it "knows" to unwind it rather than using it literally for comparison.

```javascript
let query = compiler({
  favorites: {
    $exists: {
      food: true,
      music: true
    }
  }
});

let results = records.filter(query);
//results = [{name: 'Elena', ... }]
```

#### Caveats

Object unwinding will work for all elemental operators except `$eq` and `$ne`.
When `$eq` and `$ne` receive an object, the operators will check for deep 
equality or inequality, respectively.

---

[Previous ($flatten operator)](./utility/flatten.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next (Primitives' Filtering)](./primitives-filtering.md)
