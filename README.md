Here’s an advanced JavaScript concept list for interview preparation:

1. Advanced Functions & Closures
Closures and practical use cases
IIFE (Immediately Invoked Function Expressions)
Function Currying
Function Composition
Memoization
Partial Application
Higher-Order Functions
Debouncing & Throttling (Event Optimization)
2. Asynchronous JavaScript
Event Loop & Call Stack
Microtasks & Macrotasks (Job Queue vs Task Queue)
Promises (Chaining, Error Handling, Combinators - Promise.all, Promise.race)
Async/Await (Error Handling & Performance Considerations)
Web Workers & Service Workers
Fetch API & Axios
Event Delegation
3. JavaScript Object & Prototype System
Prototype & Prototypal Inheritance
__proto__ vs prototype
Object.create() and Object Inheritance
Shallow vs Deep Copying (Object.assign(), Spread, and structuredClone)
Object.freeze(), Object.seal(), Object.defineProperty()
Garbage Collection & Memory Leaks
4. JavaScript Design Patterns
Module Pattern (CommonJS, ES6 Modules, IIFE)
Singleton Pattern
Factory Pattern
Observer Pattern (EventEmitter, Pub-Sub)
Prototype Pattern
Decorator Pattern
Strategy Pattern
5. Modern JavaScript (ES6+ Concepts)
Destructuring & Spread/Rest Operators
Template Literals
Arrow Functions (this behavior)
Optional Chaining (?.) & Nullish Coalescing (??)
Tagged Templates
Set, Map, WeakSet, WeakMap
Symbol & Its Use Cases
6. Advanced DOM Concepts
Shadow DOM & Web Components
MutationObserver API
IntersectionObserver API (Lazy Loading)
Custom Events (dispatchEvent())
Content Security Policy (CSP) Considerations
7. Performance Optimization
Repaints & Reflows (Minimizing DOM Manipulations)
Lazy Loading & Code Splitting
WebAssembly (WASM) Overview
Efficient Event Listeners
Virtual DOM Concept
8. Security in JavaScript
Cross-Site Scripting (XSS) & Prevention
Cross-Site Request Forgery (CSRF)
CORS (Cross-Origin Resource Sharing)
JSON Web Tokens (JWT) & Authentication
9. Advanced Event Handling
Event Bubbling & Capturing
Event Propagation & Stop Propagation
Custom Event Handling (CustomEvent API)
10. JavaScript Internals & Compilation
How JavaScript Code is Executed (Parsing, Compilation, Execution)
JIT Compilation (V8 Engine Concepts)
AST (Abstract Syntax Tree) in JavaScript
Tail Call Optimization (TCO)
11. Web APIs & Browser Concepts
WebSockets & Server-Sent Events
BroadcastChannel API
IndexedDB & LocalStorage Optimization
Clipboard API
File API & Drag and Drop
diff b/w splice and slice

# What is Javascript?
Its a high level Interpreted programming language used for webpage intractive, It run on the browser clint side (UI) and can run on the server side using nodejs.

# types of javscripts: 7
Primitives data types
 1. Number
 2. boolean
 3. string
 4. null
 5. undefined
 6. bigInt
 7. symbol
Non-Primitives
 1. Object
 2. Array
 3. Function
# what is function:
 building block of any programing language;

# NAN functions(Not A Number) :-
 :- It determined weather passed value is NOT A NUMBER and return true false; its types is Number

 # what is null;
 It means that no value or obj has been assigned to it;

 # different b/w undefined or null
 intensionaly declare as null where else unintialize value;

 # prompt box
 :- its  a dialog box with an optional box if users want to enter any text;

 # this keyword in js
 :- this define the currect execuation context; unlike other objects has own properties function also has own properties if this keyword is declear inside func it will change depend upon 
   how function is define or how it is envoked or default execution context; 

# What is HOF (higer order func)
a function which can take anther func (one or more) as argument or return func result of it; Its enable function programing pattern;
ex:- Map, filter, take function as argument and return result of it; 

# What is lexical scope in JavaScript?
let outer = 'I am outside!!';
function inner(){
  console.log(outer)
}
inner()

Lexical scopes: variable are refers the way variable are 

# how this keyword work in lexical scope in js;
const obj = {
  name:'Javascript';
  greet: function(){
    console.log(`Welcome ${this.name}`)
  }
}

obj.greet();
 Here in lexical scope this refered as object bcs function is called as methods; Lexical scope affect variable looksup but doesn't alter how this behaive;

# Explain how to read and write a file using JavaScript?
   readFile(path, optional, callback)
# Explain how to read and write a file using JavaScript?
   writeFile(path, data,callback)

# What is called Variable typing in JavaScript?
 type of variable used for store a number but using the same variable assign to string.
   let var = 28;
   var = 'sanjay';

# What is hoisting in JavaScript?
  nameVariable()
  console.log(x)
  var x = 7;
 function nameVariable(){
   console.log('nameste javascript');
 }
 Hoisting enable us to extract function and varaible even before initializing value without getting error, this is possible bsc of memory allocation and Execulation context;

# Memoization :- 
 memorised outer func call even outer func has executed, used for recursive or repitive task with same input;
:- Memoization is used for speeding up application up application by cache the result of expensive function call and reduce the processing time when same input is provide in the future.
function outer (){
   let count = 0;
   return function inner(){
     count++;
     console.log(count)
   }
}

const increament = outer()
increament() // 1
increament() // 2

function fib(n,memo = {}){
    if(n in memo) return memo[n]; // checking if allready computed
    if(n <= 1) return n; // base point 
    memo[n] = fib(n-1,memo) + fib(n-2,memo);
    return memo[n];
}

console.log(fib(10))

# Data Hiding and Encapsulation:
class Person {
  // private 
  #name;

  constructor(name){
    this.#name = name;
   }

   getName(name){
     return this.#name;
   }

}

const person = new Person('Sanjay')
console.log(person.getName());
console.log(person.name) // undefine

Q7: Advantage of Closure?
 1. module design pattern
 2. currying
 3. memoization
 4. setTimeout
 5. data Encapsulation etc

# splice and slice
  Splice: arr.splice(add,rem,replace) modify the original arr by adding,removing and replacing elem;
const originalArray = [1, 2, 3, 4, 5];
const removeElm = originalArray.splice(2,2,'a','b') // 3,4 // (indx,count , item1...itemX) // count and index are optional
console.log(originalArray) //  // 1,2,a, b, 5;

Slice: extract the portion of arr are return new arr without modify original arr;
const originalArray = [1, 2, 3, 4, 5];
const slice = originalArray.slice(2,4) // 3,4

# Difference between forEach(), map(), filter(), and reduce() in JavaScript
  :- each iterate over the arr; but serve a diff purpose;
  forEach(()=>{}) // execute a func in each elem but return undefine;
  map(()=>{}); // transform each elem and return new arr;
  filter(()=>{}) // return new arr with elm that passed a condition 
  reduce ((acc,elm)=>{},0) // return in single val // number, obj, arr etc;

# How do you remove duplicates from an array?
ex:- const names = ["Mike","Matt","Nancy","Adam","Jenny","Nancy","Carl"];
uniq = [new Set(names)]
 // using filter
 const uniq = names.filter((item,pos)=>  { 
    return names.indexOf(item) == pos 
 }) // [ 'Mike', 'Matt', 'Nancy', 'Adam', 'Jenny', 'Carl' ]

 //using lib;
 let result = [];
 names.forEach((item)=>{
  if(result.indexOf(item) < 0){
      result.push(item);
   }
 })

function filteredArr(arr) {
  let filteredresult = [];
  for (let i = 0; i < arr.length; i++) {
    if (!filteredresult.includes(arr[i])) {
      filteredresult.push(arr[i]);
    }
  }
  return filteredresult;

}
console.log(filteredArr(names));

 console.log(result) // [ 'Mike', 'Matt', 'Nancy', 'Adam', 'Jenny', 'Carl' ]
 What is the difference between synchronous and asynchronous programming?
 Sync: - code run line by line
      :- each task block execution until it finishes
      :- performance wise slower eg reading APIS
      :- use Case:- Simple scripts, calculations
 ASYNC :- code does not wait for task to complete,it move to next task
       :- code run in the background without blocking;
       :- faster for handling multiple tasks at once
       use Case:- API calls, file I/O, databases queries, user intractions

 # How do you deep copy an object in JavaScript?
  :- with JSON.parse(JSON.stringify(obj)) // stack overflow
  :- Object.assign({},obj) // stack overflow
  Modern js  
  let obj = {name:"sanjay",details:"age":25,city:"delhi"}
  let deepCopy = structuredClone(obj) // will create new obj recursively copying all nested obj   and arr; 
  # How do you compare two objects in JavaScript?
   var user1 = {name : "nerd", org: "dev"};
   var user2 = {name : "nerd", org: "dev"};
 console.log(JSON.stringify(user1) === JSON.stringify(user2)) // true

# What is the difference between Object.freeze() and Object.seal()?
 Object.seal : Can modify but can't add/delete;
  let obj = {name:"sanjay",age:25};
  Object.seal(obj)
  obj.sanjay = 27;
  console.log(obj) // name: 'sanjay',age: 27;
  
 : Object.freeze: completely lock
 let obj = {name:"sanjay",age: 25}
 Object.freeze(obj)
  obj.age = 28; 
  console.log(obj) // name:"sanjay",age:25 // only

# What is the difference between .call(), .apply(), and .bind()?
 Call method attaches this func and executes the function imediately;
 let person = {
  name:"Sanjay Murmu",
  greet : function(thing){
       console.log(this.name + "says hello " + thing);
  }
}
person.greet("world") // sanjay Murmu says hello world
person.greet.call({name:"Shaunjay Murmu"},"world") // Shaunjay Murmu says hello world

bind method attaches this into function and it need to be invoked seprarately 
let person = {
 name:"sanjay Murmu",
 greet: function(thing){
   console.log(this.name + "  says hello " + thing)
 }
}

const bindMethod = person.greet.bind({name:"Shaun Jay Murmu"});
bindMethod('world!') // need to invoked seprately

# Apply methods is similar to call methods but it take array-like obj instead of listing the 
arguments out, one at a time;

function personContainer() {
  let person = {
     name:"sanjay murmu",
     greet:function () {
        console.log(this.name + " says hello " + arguments[1])
     }
  }
  person.greet.apply(person, arguments) // here arguments is keywords/syntax
 }

 personContainer("world","mars"); // sanjay murmu says hello mars

# How do you convert a string to a number in JavaScript?
 :- let n = "10"
   let convertednum = parseInt(n) // +n; // 10;
# How do you check if a value is NaN?
// Number.isNaN() most reliable way to check 
Number.isNaN(NaN) // true
Number.isNaN(10) // false
Number.isNaN(undefined); false
Number.isNaN(null); // false

# What is the difference between parseInt() and parseFloat()?
 both are used to convert string into number but they return differently;
parseInt :- ingore decimal val, return NaN if no val found
parseFloat:- return exact precision, keeps decimal val if present, if no val found return NaN;

#  How do you find the largest number in an array?
let arr = [1,2,4,5,3,7,0]

# What is the difference between some() and every()?
// let numbers = [10, 25, 30, 40];
// const hasSmallVal = numbers.some((val)=> val < 20) // true
// console.log(hasSmallVal)
// let arr = [1,2,34,[1]]
// console.log(arr.flat())
// new key  is for checking intance the class methods or contructor;
// console.log([],instanceof Array)

// shallow copies : copies only top level and nested object share references
// deep copies : recursively copies all properties as well nested are fully cloned.

// windows: represent the browser window : Represent the webpage(DOM) servers side

// intermediate queestions
// Promises will return :represet future values "resolve or reject"
    // const promise = new Promise((res,rej)=>{
    //     setTimeout(()=> resolve("Done"),2000)
    // });
// async await: is a syntactic sugar over promises to handle  sync code more clearly;
// async function x(){
//     const data = await fetch("https://api.example.com");
//     return data.json();
// }
// Error handle in async await
    // using try catch to handle promise rehections;
    // async function x(){
    //     try {
    //      const res = await fetch('http://example.com');
    //      return res.json();
    //     }catch(err){
    //         console.log(err)
    //     }
    // }
    
// map(). return new arr with transformed values;
// forEach iterate over the existing arr but does not return new val;
// const arr = [1,2,3]
// const transVal = arr.map((elm)=> elm * 2) // 1,4,6
// arr.forEach(elm => console.log(elm * 2));

// fetch APis "modern" is for used for HTTP req;
// fetch("http://api.example.com")
// .then(res => res.json())
// .then(res => console.log(data))

//  generator func: - can pause function execuation using yield and resume late;
    // function* myGenerator(){
    //     yield "hello";
    //     yield "world";
    // }
    // let gen = myGenerator();
    // console.log(gen.next().value);
    
// module :- used to  split js code into reusable files using import and export;
//file 1 export function x (){console.log(x)

// file 2 import {x} from './files.js';
// x()


// // deafult exports is for single file where else named export is for multiple file with {};

//  Class Person {
    //   constructor(name){
            // this.name = name;
    //     }
    //   greet(){
    //       console.log(`Hello, ${this.name}`)
    //   }
    //  }
    
//  const person = new Person();
// person.greet()

// Propotyypes Inheritance: used for obj inherits via protypes;
// const obj = {a:10}
// const newObj = Object.create(obj)
// console.log(newObj.a) // 10; inheriated

// super is used while extends base/parent class's constructor or method;

// class Parent {
//     greet(){console.log("Hello from parent")}
// }

// class Child extends Parent {
//     greet(){
//         super.greet()
//         console.log('Hellow from child!!')
//     }
// }

// const child = new Child();
// child.greet()

// different b/w Object.create: create an obj with prototype.
// new is for call constructor func to create an obj;

// destructure: {name } = { name : 'Sanjay', age:27 }
// console.log(name) // Sanjay

// rest operator:{...} collects multiple values into an array.
// function x (...nums){
//     return nums.reduce((a,b)=> a + b, 0)
// }
// console.log(x(1,2,3))

// spread operator expends an array into individual elem;

// const arr = [1,2,3,4,]
// const ar2 = [...arr,5,6]
// arr.push(12)
// console.log(arr,"arr", ar2)

// let a = 5, b = 10;
// [a,b] = [b,a];
// console.log(a,b) // 10,5

// different b/w 
//Object.entries(): return [key, value] pairs.
//.Object.keys // return keys
// Object.values() // return values


//weakMap: used to store key - value pairs where keys are obj (weakly held);
// weakSet; store unique obj (weakly held);

// how to merge two obj in js
// let obj1 = {
//     firstname:"sanjay"
// }
// let obj2 = {
//     lastname:"Murmu"
// }

// let a_obj = {...obj1,...obj2}
// console.log(a_obj)

// Symbol data types:  unique and immitable primitives properties;
// let id = Symbol('id');
// let user = {[id]:123};
// console.log(user)

// tagged temp literals:
// custom parsing of template literals
// function tag(str,val){
//     return `${str[0]} ${val}!`;
// }

// console.log(tag`Hello ${"sanjay"}`); // remove ()


// mutable:-obj or arr that can be changes (eg: obj, arr).
// immutable: can't be changed(e.g: string,numbers)

//function constructor: used to declare variable

// memoization:- used as an redis cache to improve performance.
// function fib(n,memo={}){
//     if(n in memo) return memo[n];
//     if(n <= 1) return n;
//     memo[n] = fib(n-1,memo) + fib(n-2 + memo);
//     return  memo[n];
// }

// console.log(fib(10))



// HOF:- map, filter, forEach, reduce
// iterate over obj:- for in loop
// for(let key in obj){
    
// }

//polyfill in js:-

// event loop in js:- Handles async operations by pushing task from queue to the call stack.

// microtasks queue:- higher priority (promise.then())
// macrotasks queue : Lower priority // setTimeout()

// setTimeout(0) ; execuate after all synchronous code, as a macrotask in the event loop.
//Throttling :- limit how often a func execution in a given time;

// callback func: pass as an argument to another func as an arguments and return result once done;

// currying:- series of func arg pass exactly one arg 

// Proxy: is an obj wrap another obj and intercepts operations like getting,setting,or deleting properties.

// localStorage : data remain permanently untill cleared.
// sessionStorage:- store data only for a session once tab closed delete;
// cookies: - small data stored with expiration with HTTP requests;

# bodyParser:- Its a npm packages Its responsible for parsing incoming bodies  in a middleware before you handle it; handle for form submition;


############################################## NODE JS ################################    
# Nodejs
1. what is nodejs
Its a cross platform javascript run time, run outside the browser build on v8 chrome engine, non-blocking, event based architucture. opensourch.

2. How is Node.js different from JavaScript in the browser?
:- Js:- run in browser, Can access: access to local storage,DOM & uses: UI intraction, client side scripting language
 Nodejs: run outside the browser on server, can access:- local file OS access to databases Uses:- 

3. What is NPM
   Its node packages managers uses for packages install,update.
4. How do you create a simple Node.js server?
   const port = process.env.port || 3000
  const http = require('http')
  const http.create((req,res)=>{
    req(200,{"Content-Type":"text/javascript"})
    res.end('')
 })

 http.listen(port,(req,res)=>{
   console.log(Server is listening on ${Port})
})


 5. What is the Event Loop in Node.js?
  :- Event loop allow nodejs to handle mutliple request async without blocking the main thread.

//none blocking example
console.log('start')
setTimeout(()=>{
  console.log('setTime out!!!')
},2000)

console.log("end task!!!")

# what is the process of libuv?
:- its handle the event loop and threads pool for I/O operation

6. What are Callbacks, Promises, and Async/Await in Node.js?
 callBack :- func are pass as arguments to another func and will executed after the complication of async task eg:- fs.readFile(file,callback)
 Promises:- handle async task :- fetch().then().catch()
 Async/Await:- Clear way to handle Promise; Eg: await fetch

example for the above
 callback
 fs.writeFile('file.text','hello world',(err)=>{
  if(err) throw new Error('something went wrong!!')
  console.log('successfully data write!!')
  })

 // Promise
 const fechdata().then(res=>{console.log('done!!')}).catch('error')
 :- its a plcaeHolder for an obj untill it receive data from async operation either resolve, or reject;

 // async await
 const fetchData = async() =>{
   try{
    const response = await.fetc("https://api.example.com/data");
    const data = await response.json();
    console.log('Data!!!',data)
   }catch(err){
    console.error('something went wrong!!')
   }
 }
 
8. How to handle files in Node.js?
   const fs = require('fs');
   const data = fs.readFile('file.txt','utf8',(err,data ) => {
    if(err) throw new Error('something went wrong!!')
    console.log(data)
   })

9 What is Middleware in Express.js?
 : middleware in Express is its has access to req,res before sending it to FE, which is usally used for authenticate,

  const express = require('express')
  const app = express();

  app.use((req,res,next)=>{
  console.log('middleware executes')
   next()
  })

  app.use('/route',(req,res)=>{
   consle.log('routess')
  })

  app.listen(port,()=>{
    console.log(`app listing on ${port}`)
  })

10. What are Streams in Node.js?
 :- Streams handle data in chunk rathar then loading entire at once which is best for memory usage and performances;
Example:
 const fs = require('fs')
 const readStream = fs.createReadStream('file.txt','utf8');
 readStram.on('data',(chunk)=> {
   console.log('new Chunck:',chunk);
  });

# Type of stream 
1. Writable
2. Readable
3. Duplix
4. Transform

 3. What is closure?
    :-A closure is a func that remember the variable from its outer scope, event after the outer func has finished executing.
    eg :-
   //closure
    function outerFunction(){
      
      let count = 0;
      function innerFunction(){
        count++;
        console.log(count)
      }
      return innerFunction;
    }
    
    const count = outerFunction()
    count() // 1
    
    count() //2

//clouser used cases
for(var i = 0;i<3;i++){
  ((x)=>{console.log(x)})(i)
}

//Practicle use case of clousure;
function bankAccount(initialAmount) {
  //initial anount;
  let balance = initialAmount; // private var;
  
  return {
    deposite: function(amount){
      balance+=amount;
    },
    
    withDraw: function(amount){
        if(balance < amount){
          console.log(`Insufficient ${balance}`)
          return;
        }
        balance+= amount
        console.log(`You have ${balance} left in your account`)
    },
    
    currBalance(){
      console.log(`YOu have ${balance} in your current account!!`)
    }
    
    
  }
  
}

const myAccount = bankAccount(100);
myAccount.deposite(200);
myAccount.withDraw(500);
myAccount.currBalance();


# Function Currying
// currying used in js complex function call breaking down into smaller,more manageable steps. it transform a func with multiple argument into a series of func each taking a single
argument.
const add = a => b => a+b;
console.log(add(5)(4));

# advantage:
 1. hepls in create HOF;
 2. It reduces the changes of error in our func by dividing it into multiple smaller func that can handle one responsibility.
 3. Used for building modular and reusable code
 4. code more readable;

# Function Composition 
Its a technique in function programing where multiple function are combined to form /create new function
or 
Istead of writing big nested func Function composition transfer into more readable,clearer,one task one func and that one single task func can be reusable;

ex:- 
 Suppose you want to double a number and then add 5 to it.
function double(num){
 return num * 2
}
function addFive(num){
  return num+5
}

 console.log(addFive(double(5)));

 # Partial Application in JS
 :- functinal programming techinque where we fix some arguments of a function in advance with few paraments
 ex:- Pizza you decide type of pizza:'Margherita';
 later you specify size and toppings
 function totalCost(price,quantity,tax){
  return price * quantity * (1+ tax)
 }

 //partial apply tax
 const withTax = (price,quantity) => totalCost(price,quantity,0.1);
 console.log(withTax(100, 2)); // Output: 220
console.log(withTax(50, 3));  // Output: 165

# Higher-Order Function(HOF) in javascript
HOF take another function as argument and return a result.

function double(num){
 return x*2;
}
function processNumber(func,num){
  return func(num);
}
console.log(processNumber(double,5)) //Output: 10;

# Debouncing & Throttling (Event Optimization)
Imagine you’re typing in a search box, and after every keystroke, a function makes an API request to get results.

🚨 Problem: Too many function calls happen too quickly, slowing down the app and overloading the server.

💡 Solution? We use Debouncing and Throttling to control how often a function executes.

:- Debouncing delay the function execution untill the user stops triggering the events.

function debounce(func,delay){
  return function (...args){
    clearTimeout(timer);
    timer = setTimeout(() => func(...args),delay)
  }
}

function searchQuery(){
 console.log('Featching search results....')
}

const debounceSearch = debounce(searchQuery,5000)

#  Asynchronous JavaScript
 :allow non blocking opertion to execuate while enabling other task continue execuation with waiting for  eg API call, file operation etc.

# What is async function and how it is different from normal function?
:- async function will always return promise even string is return from func;
 Normal function will return any data types including promises but it doesn't return automatically;

//async
async function x(){
  return "Nameste Javascript"
}
const dataPromise = x()
console.log(dataPromise) // promise { Nameste Javascript }

//❓How to extract data from above promise? One way is using promise .then
dataPromise.then(res => console.log(res)); // Namaste JavaScript

#What makes async-await special?
:- code readibility and error handling using try catch
:- ovide callback hell


# what in process.next.Tick()
 : it run as soon as the currect execution complete; but before the event loop countinue
console.log('start')
process.nextTick(()=>{
 console.log('Inside nextTick')
})
console.log('end')

# setImmediate()
: it run after current execution complete, event when in the check phase in the current loop
let start = "start";
setImmediate(()=>{
 console.log("run set Immediate")
})

console.log("End")
output:
 start
 end
 run  set Immediate

# setTimeout(fn,0)
: run after minimun delay in the timer phase; schedule something after a minimum delay;

# interviewPreparation-2025

console.log("Start");

setTimeout(() => {
  console.log("setTimeout");
}, 0);

setImmediate(() => {
  console.log("setImmediate");
});

process.nextTick(() => {
  console.log("nextTick");
});

console.log("End");

// Start
// End
// nextTick //always runs before other async callbacks.
//setTimeout
//setImmediate 
# setTimeout and setImmediate may swap depending on the system, but generally, setTimeout goes first when both are in the main script.


SYSTEM DESIGN QUESTION:-
  Stangler Design Pattern:- break into small parts and ship from monolathic to microservices 
  ex:- Restraunt : planing to create new kitchen and start cooking it start from single item once that ship well then gradually other items will 
  be cook there.

# 1. HLD :- High Level design
main components that would be develop for the resulting product

# 2. LLD:- Low level Design
Desing for each elem mentioned in the High - level Design of the system
classes, interfaces,relationship b/w class and actual logic of the various components

Monolithic architure:-(internal design):- single codebase/same repo;
bcs:- lesss complexity, easier to understand,high productivity also known as centralised system so it require less network calls as compare to other arch;

Disadvantages:-
1. if error or bug it can destroy the complete system;
2. If single module updated whole system neeed to be updated to reflect changes;
3. If module programming language or framework changed entire system need to be changed;

website:- blog:- only read
webApplication:- write + read

# Distributed system:-
collection of multiple individual system connected through a network that share resources,communicate and coordinate to achieve common goal

Advantage:-
1. scalable
2. No single point of failure
3. low latency;

disAdvantage:-
1. Complex
2. Manage resources
3. difficult to secure
4. message might be lost in b/w nodes

# Latency: network delay + computation delay ;
how to reduce latency:- by using 1. caching,:- store info for a set of period of time on a computer.
2. CDN "Content delivery networks" which is distrubuted network of proxy servers obj is to serve content to users more quickly;

# Throughput:- vol of work through a system / per sec; measure in bps bits per sec;
how to improve :-
 1. using CDN
 2. caching
 3. distributed system
 4. load balancer
 5. improve resources

# Availability:- eg cbse result website down Make sure website is avaiable all the time like 
google;

# Where services will be able to get you most availabity;
 1. Monolithic Architecture : if server break down all the availibility will goes down; fault Tolerance is directly propertional to availabity;
 2. Distributed system:- Most availibity will the there in distributed system bcs if one server fail, repilcate will serve by that time;

Replication:-Include redundancy but involves copying of data from one node to another
or the synchronization of the state b/w nodes;

# Redundancy:-duplication of nodes in case of some of them are failing

# Consistency:- When more then one client req the system,for all such req it will be called consistent when each client get the same data, the data should be consistent,regardless of who is accessing it.
eg:- movie ticket buys;
Factor Improving Consistency:
 1. Improve Network bandwidth
 2.  stop the read operation "untill all db is updated"
 3.  Replication based on distance aware strategies;

types of consistency
1. Strong Consistency
  :- When system doesn't allow read operation untill all the nodes with replicated data are updated ;
2. Eventual Consitency:-reads are not halted till all the replicas are updated rather
the update process is eventual. some user might receive old data but eventually all the data is updated to the latest data;
3. Weak Consistency: No consistency within the nodes

# CAP Theorem :- for a distributed System the CAP Theorem state that it is possible to attain only two properties and the third would be compromised.
C:- consistence
A:- Availability
P: Partition Tolerance (most importance) :- distributor server  
here:-CAP theorm is only allowed either CP or AP Not CA bcs Partion Tolerance is important in distributor server;

# What is Lamport Clock:- TO check time zone eg if we have three server in different time zone
to get exact time data update it is measure using lamport clock;

# Scalability:-

# Top PostgreSQL Interview queston with answers
1. what is PostgreSQL:-
Ans:- Ist Free, open source, relational database, support SQL and advance feature like JSON, Indexing, text-base-search;
2. Different b/w PostgreSQL and SQL
   PostgresSQL is a database its support SQL to intract with data
   SQL is a Structured Query Language

3. Table
   CREATE TABLE users(
    id serial PRIMARY KEY
    name TEXT,
    email: TEXT UNIQUE
   )

4. Primary key :- its a column that uniquely Identifies each row in a table.
5. Foreign Key : Its connect two tables, It ensure data in table matches a value in another table;

CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name TEXT IS NOT NULL,
  email: TEXT
)

CREATE TABLE orders (
  id serial PRIMARY KEY,
  product_name TEXT,
  user_id INT,
  FOREIGN KEY (user_id) REFERENCE users(id)
)

// Insert a user 
INSERT INTO users(name, email) VALUES ("SANJAY","sanjaymurmu@gmail.com");

--Inser an order for that user
INSERT INTO orders(product_name) VALUES("Laptop", 1);

# LIMIT 
select * from users LIMIT 5;

# update data in table
UPDATE users SET name = "ShaunJay" where id = 1;

# Fetch
SELECT * FROM users;

# Index in PostgreSQL
CREATE INDEX idx_email ON users(email);

# Types of Joins in PostgreSQL
1. LEFT JOIN :- All from the left and only matching rows from right
2. RIGHT JOIN : All from the right and only matched from left;
3. INNER JOIN : Only matching rows
4. FULL JOIN : All rows from sides

SELECT u.username, o.product
FROM users u
LEFT JOIN orders o ON u.id = o.user_id;

# RIGHT JOIN
SELECT u.username,o.product
FROM users u
RIGHT JOIN orders ON u.id = o.user_id;

# INNER JOIN 
SELECT u.name, o.product
FROM users u
INNER JOIN oders o ON u.id = o.user_id;

# Full Join


# Transaction?
Its a group of operation that run together If one fails all are rolled backed. 
BEGIN;
UPDATE users set roll_no = roll_no - 100 where id = 1;
UPDATE user set roll_no = roll_no + 100 where id = 2;
COMMIT;
