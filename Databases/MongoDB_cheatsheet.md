# MongoDB cheatsheet

## Create USER
```mongo
db.createUser({user: "sadmin",pwd: passwordPrompt(),roles: [ { role: "userAdminAnyDatabase", db: "admin" }, "readWriteAnyDatabase" ]})
```
## Queries
