## Mongo Query Compiler Documentation

### Operator Types

`mongo-query-compiler` supports three types of operators: elemental, logical, 
and utility.  

Elemental operators can be further categorized into primitive, array, free-form, 
and specialty.  These are called elemental because they can be applied only to 
an object element's value.  Search criteria defined for an elemental **cannot** 
nest any primitive or logical operators.

Logical operators allow joining simpler queries to form complex filtering 
parameters.  Search settings set for a logical could and should nest other 
appropriate operators.

Utility modifiers add supplemental query information and control search criteria 
execution.

---

[Previous (Query Grammar)](./query-grammar.md) :snowflake: 
[Table of Contents](../README.md) :snowflake: 
[Next (Accessing Object Elements)](./accessing-object-elements.md)
