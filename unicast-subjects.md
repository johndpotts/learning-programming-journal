
const observable = rxjs.Observable.create((observer) => {
    observer.next(Math.random());
});

const subject = new rxjs.Subject();

subject.subscribe((data) => {
console.log(`Subject subscriber 1 recieves ${data}`)
})

subject.subscribe((data) => {
console.log(`Subject subscriber 2 recieves ${data}`)
})

// subscription 1
observable.subscribe((data) => {
  console.log(`Observable subscriber 1 recieves ${data}`); // 0.24957144215097515 (random number)
});

// subscription 2
observable.subscribe((data) => {
     console.log(`Observable subscriber 2 recieves ${data}`); // 0.24957144215097515 (random number)
 // 0.004617340049055896 (random number)
});

subject.next(Math.random()); 
