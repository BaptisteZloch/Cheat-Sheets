# Express cheat sheet

## Express Installation
Preparing environnement :
```bash
$ mkdir myapp
$ cd myapp
```
Initialize package.json :
```bash
$ npm init
```
Install Express and add it to dependancies :
```bash
$ npm install express --save
```

## Express sample
Basic strcuture :
```js
const express = require('express')

const app = express()

const portListen = 3000

app.get('/', function (req, res) {
    res.send('Hello World!')
   })

app.listen(portListen, function () {
console.log('Your API is available on : http://localhost:3000 !')
})
```
Post sample :
```js
app.post('/addUser', jsonParser, async (req, res) => {
    console.log("User's mail adress"+req.body.mail);
    ...//add user using controler and collection
    return res.status(201).json({message: 'user created'});})
})
```
## Tricks
- To get parameter from the request (get):
```js
req.query.<variable_name>
```
- To render html
```js 
app.use(express.static("public")); //to server static files
```
or
```js
res.sendFile(path.join(__dirname, "public/index.html"));
```
