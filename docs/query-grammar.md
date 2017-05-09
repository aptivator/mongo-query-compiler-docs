## Mongo Query Compiler Documentation

### Query Grammar

`mongo-query-compiler` supports mongodb syntax and augments it with new features 
such as query namespaces, new operators, and different ways to specify search 
parameters.  The grammar employed by the tool is more flexible and allows a more 
economical declaration of criteria.  For example, `$and` statements can be set 
as an object of queries and also as a typical array of queries.  This guide 
presents examples of both usages.

---

[Previous (Introduction)](./introduction.md) :snowflake: 
[Table of Contents](../README.md) :snowflake: 
[Next (Operator Types)](./operator-types.md)
