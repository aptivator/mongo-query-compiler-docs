## Mongo Query Compiler Documentation

### $comment

Allows for comments to be added to queries.

```javascript
let query = {
  $comment: 'Find employees who worked less than 40 hours',
  $where(o, browser) {
    let {timeSheet} = this;
    let sum = timeSheet.reduce((sum, hours) => sum += hours);
    return sum < 40;
  }
};
```

---

[Previous ($not operator)](../logical/not.md) :snowflake: 
[Table of Contents](../../README.md) :snowflake: 
[Next ($flatten operator)](./flatten.md)
