## Mongo Query Compiler Documentation

### $options

`$regexp`- and `$regex`-dependent operator that specifies 
search flags to use with a string-only regular expression.

At this time, only MongoDB's `i`, `m`, and `s` flags overlap
with JavaScript regular expression options.  MongoDB's `x`
flag is not supported.

```javascript
let records = [
  {name: 'Igor'},
  {name: 'ivan'}
];

let query = {name: {$regexp: '^i', $options: 'i'}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = [{name: 'Igor'}, {name: 'ivan'}]
```

`$options` must be specified on the same level inside a query
object as `$regexp`.  Failure to do so will produce incorrect
results.

```javascript
let query = {$regexp: {name: '^i', $options: 'i'}};
let filterer = compileMongoQuery(query);
let results = records.filter(filterer);
//results = []
```

---

[Previous ($regex operator)](./regex.md) :snowflake: 
[Table of Contents](../../../README.md) :snowflake: 
[Next ($type operator)](./type.md)
