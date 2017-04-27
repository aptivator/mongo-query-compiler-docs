## Mongo Query Compiler Documentation

### $and

Determines if several criteria listed within the `$and` clause are all fulfilled.
`mongo-query-compiler`, unlike mongodb, allows `$and` query to be specified as
either an object or an array of queries.

```javascript
/* $and as an object of queries */

let records = [{
  name: 'Ivan',
  age: 27,
  cars: [
    {brand: 'toyota', model: 'camry', year: 2008},
    {brand: 'nissan', model: 'sentra', year: 2010}
  ]
}, {
  name: 'Charlie',
  age: 57,
  cars: [
    {brand: 'acura', model: 'tl', year: 2015}
  ]
}];

let query = compiler({$and: {age: {$gt: 30}, cars: {brand: {$eq: /^acu/}}}});
let results = records.filter(query);
//results = [{name: 'Charlie', ... }]
```

```javascript
/* $and as an array of queries */

let records = [
  {name: 'Bill', yearBorn: 1980},
  {name: 'Joane', yearBorn: 1981},
  {name: 'Stuart', yearBorn: 1970}
];

let query = compiler({yearBorn: {$and: [{$gt: 1970}, {$mod: [4, 0]}]}});
let results = records.filter(query);
//results = [{name: 'Bill', yearBorn: 1980}]
```

---

[Previous (implicit $and operator)](./implicit-and.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next ($or operator)](./or.md)
