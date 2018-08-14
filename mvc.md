One of the most common patterns in software design is called the MVC (Model - View - Controller). 
The goal of this pattern, as with most good software design, is to provide a separation of concerns 
between different parts of an application.
***
### maintaining a separation of concerns means that each part of an application should be concerned with only its own area of responsibility
***


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
The three parts of an MVC pattern are as follows:

### 1. The Model
```js
const model = {
  groceryList: []
}
```

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


### 3. The View
```js
const view = {
  readList: function(list){
    console.log(`Here is your ${list}`)
   model[list].forEach(item => console.log(item))
  }
```



In the real world, there are a number of variations on the MVC theme. There is the M
