The Singleton design pattern

The Singleton design pattern is a very common pattern in Javascript. In fact, if you've written any significant amount of code in JS you've probably used it (even if you didn't know it!)

There are many analogies that can be used to help understand the singleton pattern, but one of my favorites is that of a a shared printer. Imagine an office floor with dozens of employees sitting at desks - now imagine each of these employees has a small desktop printer. The office could function with this setup, but there are problems with this approach. Dozens of printers means dozens of maintenance schedules to follow, dozens of updates to perform, and dozens of places where problems could happen. 

Our imaginary office would be much more efficient if all the employees could share a single, more robust printer with a common job queue. The printer might be a bit more complicated to set up initially since it would need to deal with more than just one input, but it would allow us to easily scale and modify our office's printing needs.

The shared printer in this analogy is a great example of a singleton. One, shared resource that has an interface exposed to the rest of the application.

In the Angular framework, many services are registered at the app module level and set up as singletons (the Angular Router being one example). In vanilla JS, singletons are generally set up as globally accessible namespaces. The JQuery is one example of a well-known singleton pattern. 

js```
let singletonInstance = null;

class Singleton {
  constructor() {
    // Check if the instance exists or is null
    if (!singletonInstance) {
      // If null, set singletonInstance to this Class 
      singletonInstance = this;
      console.log('singleton instance created')
    } else {
      console.log('you are referencing the existing singleton class');
    }
    // Returns the initiated Class
    return singletonInstance;
  }

  speak(){
    console.log('hello')
    }
}

// Create a new instance of singleton Class
let singleton1 = new Singleton();
let singleton2 = new Singleton();

singleton1.speak();
// 'hello'
singleton2.speak();
// 'hello'
console.log(singleton1 === singleton2)
// true
```
