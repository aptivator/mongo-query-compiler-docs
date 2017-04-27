## Mongo Query Compiler Documentation

### Elemental Operations and Element's Existence

It is important to note that all non-negating elemental operations (e.g., `$eq`, 
`$lt`) will automatically return `false` if an object element does not exist.
All negating operations (i.e., `$ne` and `$nin`) will automatically return 
`true` if an object element does not exist.

