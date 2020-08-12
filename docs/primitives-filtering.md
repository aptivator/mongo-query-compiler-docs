## Mongo Query Compiler Documentation

### Primitives' Filtering

`mongo-query-compiler` was written to simplify filtering of an array of objects.
The tool can be used with equal success to filter an array of non-objects.

```javascript
let scores = [55, 88, 91, 87, 61];

let query = {$and: {$gte: 70, $lte: 90}};
let filterer = compileMongoQuery(query);
let results = scores.filter(filterer);
//results = [88, 87]
```

---

[Previous (Query Namespacing and Unwinding)](./query-namespacing-unwinding.md) :snowflake: 
[Table of Contents](../README.md) :snowflake: 
[Next (Caveats)](./caveats.md)
