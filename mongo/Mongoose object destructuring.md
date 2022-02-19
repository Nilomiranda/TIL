After querying for a document in the mongo database like this:

```typescript
const user = User.findOne()
```

You may want to work wit this data, such as object destructuring:

```typescript
const updatedUser = {
	...user,
	name: 'Danilo',
}
```

You will have some unexpected behaviour like getting some internal properties from the mongo document instance, and even **lose** the real data you want to work with:

```typescript
{
	'$__',
    InternalCache {
      strictMode: false,
      selected: [Object],
      shardval: undefined,
      saveError: undefined,
      validationError: undefined,
      adhocPaths: undefined,
      removing: undefined,
      inserting: undefined,
      saving: undefined,
      version: undefined,
      getters: {},
      _id: 5f60647c28b90939d0e5fb24,
      populate: undefined,
      populated: undefined,
      wasPopulated: false,
      scope: undefined,
      activePaths: [StateMachine],
      pathsToScopes: {},
      cachedRequired: {},
      session: undefined,
      '$setCalled': Set(0) {},
      ownerDocument: undefined,
      fullPath: undefined,
      emitter: [EventEmitter],
      '$options': [Object]
    }
  ],
  [ 'isNew', false ],
  [ 'errors', undefined ],
  [ '$locals', {} ],
  [ '$op', null ],
}
```

To solve this, you first need to convert this mongo document reference to a plain javascript object.

There's two ways of doing it

- Using `.lean()`
	- [Docs](https://mongoosejs.com/docs/api.html#query_Query-lean)
- Using `user.toObject()`
	- [Docs](https://mongoosejs.com/docs/api.html#document_Document-toObject)