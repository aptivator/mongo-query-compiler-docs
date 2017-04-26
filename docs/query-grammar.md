## Mongo Query Compiler Documentation

### Query Grammar

`mongo-query-compiler` supports mongodb syntax and augments it with new features 
such as query namespaces, new operators, and new ways to specify search criteria.
The grammar employed by the tool is more flexible and allows a more economical 
specification of criteria.  For example, `$and` statements can be specified as 
an object of queries and also as a typical array of queries.  This guide presents
examples of both usages.

---

[Introduction](./introduction.md) :snowflake: 
[Table of Contents](../README.md) :snowflake: 
[Operator Types](./operator-types.md)
