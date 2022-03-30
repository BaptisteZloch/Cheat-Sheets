# MongoDB cheatsheet

## Create USER
```mongo
db.createUser({user: "sadmin",pwd: passwordPrompt(),roles: [ { role: "userAdminAnyDatabase", db: "admin" }, "readWriteAnyDatabase" ]})
```
For root user of database
```mongo
db.createUser({user: "admin",pwd: passwordPrompt(),roles: [ { role: "root", db: "admin" }, "readWriteAnyDatabase" ]})
```
## Queries
