# jQuery Cheat sheet


## Call DOM elements
### Call by ID
To call an element you have to add an id to the HTML element. Like this :
```html
  <a href='/hello-world' class='link' id='mylink'>Click me</a>
```
You can call it into the JavaScript code like this :
```js
  $('#mylink')
```
It will return the element, one element only.

### Call by class
To call an element you have to add a class to the HTML element. Like this :
```html
  <a href='/hello-world' class='link' id='mylink'>Click me</a>
```
You can call it into the JavaScript code like this :
```js
  $('.link')
```
It will return all the elements having this class into an array.

### Call by XPath
To call an element you have to add a class to the HTML element. Like this :
```html
  <tr>
    <td>data1</td>
    <td name="tcol1" class="bold"> data2</td>
  </tr>
  <tr>
    <td>data1</td>
    <td name="tcol1" class="bold"> data2</td>
  </tr>
  <tr>
    <td>data1</td>
    <td name="tcol1" class="bold"> data2</td>
  </tr>
```
```js
  $('td[name="tcol1"]')   // Matches exactly 'tcol1'
  $('td[name^="tcol"]' )  // Matches those that begin with 'tcol'
  $('td[name$="tcol"]' )  // Matches those that end with 'tcol'
  $('td[name*="tcol"]' )  // Matches those that contain 'tcol'
```
It will return all the elements having this XPath into an array or only one element if there is only one element that matchs it.

## DOM manipulation


### Modify an attribute
```js

```

### Change the style
```js

```


## Event Listener


```js

```


## Ajax & Requests


```js

```
