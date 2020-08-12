### Caveats

For performance reasons, it is recommended that the query functions be prebuilt
rather than compiled every time an array is filtered.  

The grammar implemented by `mongo-query-compiler` subsumes the grammar used by
mongodb and provides new features such as query namespacing, query unwinding, 
and new operators such as `$ref` and `$flatten`.

The tool **will not** display an error if an invalid operator is used.  An
invalid operator name will be treated as an object element.

```javascript
/* query with a non-supported operator */

let query = {
  records: {
    $something: 22
  }
};
```

The above query will be understood the same as:

```javascript
let query = {'records.$something': 22};
```

---

[Previous (Primitives' Filtering)](./primitives-filtering.md) :snowflake: 
[Table of Contents](../README.md)
