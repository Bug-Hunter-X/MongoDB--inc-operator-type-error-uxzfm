# MongoDB $inc operator type error
This repository demonstrates a common error when using the `$inc` operator in MongoDB update operations. The `$inc` operator is used to increment a numerical field by a specified value. However, if the value provided is not a number (e.g., a string), the operation will fail or produce unexpected results.

## Bug
The following code snippet shows the incorrect usage of the `$inc` operator:
```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: '1' } });
```
In this example, the `count` field is attempted to be incremented by the string value `'1'`, instead of the number `1`. This results in an error or unexpected behavior depending on the MongoDB driver and settings.

## Solution
The correct usage involves providing a numerical value to the `$inc` operator:
```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: 1 } });
```
This code snippet correctly increments the `count` field by 1.