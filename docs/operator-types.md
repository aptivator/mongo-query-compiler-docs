## Mongo Query Compiler Documentation

### Operator Types

`mongo-query-compiler` supports three types of operators: elemental, logical, 
and utility.  

Elemental operators can be further categorized into primitive, 
array, free-form, and specialty.  These are called elemental because they can 
be applied only to an object element's value and search criteria defined for an 
elemental **cannot** nest any primitive or logical operators.  

Logical operators allow joining simpler queries to form complex filtering 
criteria.  Search parameters specified for a logical could and should nest other 
appropriate operators.

Utility modifiers add suplemental query information and controll search criteria 
execution.

---

[:arrow_backward:Query Grammar](./query-grammar.md) :snowflake: 
[Table of Contents](../README.md) :snowflake: 
[$exists operator](./elemental/primitive/exists.md)
