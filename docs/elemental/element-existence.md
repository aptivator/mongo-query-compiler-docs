## Mongo Query Compiler Documentation

### Elemental Operators and Element's Existence

Object element existence is determined by checking if the object's keys include 
the assessed element's name.  Do note that all non-negating elemental operations 
(e.g., `$eq`, `$lt`) will automatically return `false` if an object element does
not exist. (An object element's value cannot be compared to anything if the 
element is not included in an object).  All negating operations (i.e., `$ne` and
`$nin`) will automatically return `true` if an object element does not exist.

[Previous ($ref operator)](./specialty/ref.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next (implicit $and operator)](../logical/implicit-and.md)
