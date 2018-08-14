One of the most common patterns in software design is called the MVC (Model - View - Controller). This pattern (and its many variations) exist across a wide spectrum of programming languages and frameworks.
The goal of the MVC pattern is to provide a separation of concerns between different parts of an application.

***
### maintaining a separation of concerns means that each part of an application should be concerned with only its own area of responsibility
***

One of the easiest ways to conceptualize the MVC pattern is to think about a web app that is comprised of three parts: a database for storing information, client side code that renders a view, and a server that handles communication between the two. Each of these parts should handle their own responsibility well. In this example, the model doesn't need to know anything about the view; it is only concerned with the data. The view doesn't edit the data; its only concern is rendering the data in a way the user can understand.

Here is a very basic example of an MVC pattern in vanilla javascript:
```js
const model = {
  groceryList: []
}

const view = {
  readList: function(list){
    console.log(`Here is your ${list}`)
   model[list].forEach(item => console.log(item))
  }
}

const controller = {
remove: function(itemName, list) {
    model[list] = model[list].filter(
      name => name !== itemName
      )},
  add: function(itemName, list) {
    model[list].push(itemName)
  }
}


controller.add('apples', 'groceryList');
controller.add('milk', 'groceryList');
controller.add('eggs', 'groceryList');
view.readList('groceryList'); 
// here is your groceryList:
// apples
// eggs
// milk


controller.remove('eggs', 'groceryList');
view.readList('groceryList');
// here is your groceryList:
// apples
// milk

```


Let's take a closer look at each part of our application:

### 1. The Model
```js
const model = {
  groceryList: []
}
```
In this case, all the model does is hold data. In an actual application the model would certainly be more complicated than this, but the same idea remains - the model doesn't know, and doesn't care, about how the data is displayed. There could be one view or a thousand views; the model operates independent of them.


### 2. The Controller
```js
const controller = {
remove: function(itemName, list) {
    model[list] = model[list].filter(
      name => name !== itemName
      )},
  add: function(itemName, list) {
    model[list].push(itemName)
  }
}
```

The controller in our application takes user input and alters the data in the model. It is not in charge of rendering the view; it just tells the model to change based on user input. Our controller here has two functions: **remove** which removes the item(first argument) from the desired list(second argument) and **add** which adds the item(first argument) to the specified list(second argument).


### 3. The View
```js
const view = {
  readList: function(list){
    console.log(`Here is your ${list}`)
   model[list].forEach(item => console.log(item))
  }
```
Our view doesn't keep track of the data or perform any operations on the data; it simply takes care of rendering it in a way the user can understand. In this case the view's only function is readList, which console.logs a heading with the list name, then console.logs each item on the list.

Should the view read directly from the model or access te model through the controller? In a more complex application it would probably be better for the view to access the model through the controller (thus giving us the ability to do things like changing out different models), but it's also a valid application of the MVC pattern for the view to read directly from the model; it just can't perform any operations on the model.


In the real world, there are a number of variations on the MVC theme. There is the M
