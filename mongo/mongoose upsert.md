If you want to execute an `upsert` operation using mongoose, you can use the `findOneAndUpdate` method.

```javascript

MongooseModel.findOneAndUpdate(findConditions, schemaData, { upsert: true })
```

Notice the third parameters `options`. We set the property `upsert: true` so we tell that if no record is found based in the conditions passed in `findConditions` we want to **create and insert** a new record.

Example:

```javascript
UserModel.findOneAndUpdate({ _id: 1 }, { name: 'Danilo Miranda' }, { upsert: true })
```