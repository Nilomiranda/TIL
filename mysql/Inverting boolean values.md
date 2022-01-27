You can invert a boolean value in a MySQL statement (e.g.: `true` => `false`, `false` => `true`).

```sql
UPDATE TABLE_NAME
   SET BOOLEAN_FIELD = NOT BOOLEAN_FIELD
WHERE CONDITION_FOR_THE_UPDATE
```