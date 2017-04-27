### Conclusion

For performance reasons, it is recommended that the query functions be prebuilt
rather than compiled every time an array is filtered.  Also note that the 
grammar implemented by `mongo-query-compiler` is different from mongodb query 
grammar and a developer is encouraged to consult this document to be aware of 
the differences between the two implementations.
