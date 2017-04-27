## Mongo Query Compiler Documentation

### Elemental Operators and Element's Existence

It is important to note that all non-negating elemental operations (e.g., `$eq`, 
`$lt`) will automatically return `false` if an object element does not exist. An
object element's value cannot, for example, equal to anything if the element 
does not exist.  All negating operations (i.e., `$ne` and `$nin`) will 
automatically return `true` if an object element does not exist.

[Previous ($ref operator)](./specialty/ref.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next (implicit $and operator)](../logical/implicit-and.md)
