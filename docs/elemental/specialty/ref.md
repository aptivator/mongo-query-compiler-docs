Instead of specifying a comparator value, a reference may be used, which is an 
address to one of the object's elements.  Reference inclusion is supported for 
all the primitive operators listed in this section: `$gt`, `$gte`, etc.

```javascript
/* reference equality */

let records = [
  {lastName: 'Johnson', maidenName: null},
  {lastName: 'Jones', maidenName: 'Clarkson'},
  {lastName: 'Smith', maidenName: 'Smith'}
];

let query = compiler({lastName: {$eq: {$ref: 'maidenName'}}});
let results = records.filter(query);
//results = [{lastName: 'Smith', maidenName: 'Smith'}]
```

**Note:** `$ref` operator is not supported by mongodb.