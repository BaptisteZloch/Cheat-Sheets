# jQuery Cheat sheet


## Call DOM elements
This part could be called **querySelector**.
### Call by ID
To call an element you have to add an id to the HTML element. Like this :
```html
  <a href='/hello-world' class='link' id='mylink'>Click me</a>
```
You can call it into the JavaScript code like this :
```javascript
  $('#mylink')
```
It will return the element, one element only.

### Call by class
To call an element you have to add a class to the HTML element. Like this :
```html
  <a href='/hello-world' class='link' id='mylink'>Click me</a>
```
You can call it into the JavaScript code like this :
```javascript
  $('.link')
```
It will return all the elements having this class into an array.

### Call by HTML element
To call an element you just have to declare it into the HTML code.
```html
  <p>Hello World</p>
```
You can call it into the JavaScript code like this :
```javascript
  $('p')
```
It will return all the p elements in an array.

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
```javascript
  $('td[name="tcol1"]')   // Matches exactly 'tcol1'
  $('td[name^="tcol"]' )  // Matches those that begin with 'tcol'
  $('td[name$="tcol"]' )  // Matches those that end with 'tcol'
  $('td[name*="tcol"]' )  // Matches those that contain 'tcol'
```
It will return all the elements having this XPath into an array or only one element if there is only one element that matchs it.

## DOM manipulation
### Modify an attribute
To modify an attribut of an HTML tag you have to first call an element by **XPath**, **class**, **id**, **name**, or HTML element (be carefull arrays it accepts only one element). Then you call the function `attr()`, that takes as first input the attribut you want to modify and in the second argument the value.
```javascript
  $('p').attr('hidden', 'hidden'); //all the paragraphs will be hidden
  $('input').attr('required', 'required'); //all the inputs will be required
  $('#myImg').attr('src', './path/to/image.png'); //an img HTML element with the id=MyImg will have ./path/to/image.png image as src
```

### Remove an attribute
Then sometimes you want to remove and attribut of an HTML element. You simply have to call the `removeAttr()` function.
```javascript
  $('p').removeAttr('hidden'); //all the paragraphs will be visible
  $('input').removeAttr('required'); //all the input will be unrequired
```

### Change the style
To change the style you have to first call an element by **XPath**, **class**, **id**, **name**, or HTML element (be carefull arrays it accepts only one element). Then you call the css function that takes as input a key-value table where the key is the **CSS attribut** (like `background-color, font-family, font-size...`) and the value is the value you want to put (like `3px, green, #fff, 'arial sans-serif'...`).
```javascript
  $('p').css({"color": "yellow", "font-size": "xx-large"});
```
Here all the paragraphs will be written in large format and in yellow.

## Event Listener
If you want to trigger some action when events happen, use event listner. jQuery provides a lot of function you have to call after a querySelector. You have 2 choices :
### Simple Trigger
#### 1. Using the method natively
You can call directly the function on the event right after the querySelector. The function takes as input only the function (also called a **callback**) to execute when event occurs.
```javascript
  $('#myButton').click({
      console.log('you clicked on that button');
      /*
      ...
      do something here like DOM manipulation or some Ajax requests....
      ...      
      */
  });
```
Here the exemple is when the HTML element button with `id='myButton'` is clicked. However there are a lot of functions such as `dblclick(), hover(), keyup()...`. Yo ucan find a list [here](https://www.w3schools.com/jquery/jquery_ref_events.asp).
#### 2. Using the method in a string
Or you can call directly the function `on()` after the querySelector that takes as input a string with the event and a second input the function (also called a **callback**) to execute when event occurs.
```javascript
  $('#myButton').on('click',{
      console.log('you clicked on that button');
      /*
      ...
      do something here like DOM manipulation or some Ajax requests....
      ...      
      */
  });
```
Here the exemple is when the HTML element button with `id='myButton'` is clicked. However there are a lot of functions such as `dblclick, hover, keyup, change...`. You can find a list [here](https://www.w3schools.com/jquery/jquery_ref_events.asp).
## Ajax & Requests


```javascript

```
