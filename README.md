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
a function which can take onther func (one or more) as argument or return func result of it; Its enable function programing pattern;
ex:- Map, filter, take function as argument and return result of it; 

# What is lexical scope in JavaScript?
let outer = 'I am outside!!';
function inner(){
  console.log(outer)
}
inner()

Lexical scopes: variable are refers the way variable are 

# how  this keyword work in lexical scope in js;
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
   function inner(){
     count++;
     console.log(count)
   }
}

outer()
couter()

function fib(n,memo = {}){
    if(n in memo) return memo[n];
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
  :- each iterate over the arr; but server a diff purpose;
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
  :- Event loop allow nodejs handle mutliple request async without blocking the main thread.

//none blocking example
console.log('start')
setTimeout(()=>{
  console.log('setTime out!!!')
},2000)

console.log("end task!!!")

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
 :- Streams handle data in chunk to improve performances;
Example:
 const fs = require('fs')
 const readStream = fs.createReadStream('file.txt','utf8');
 readStram.on('data',(chunk)=> {
   console.log('new Chunck:',chunk);
  })
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
Currying is a technique in function programing where function is transfer into sequnce of nested function and where each function carrying single arugment; 
// currying used in js complex function call breaking down into smaller,more manageable steps. it transform a func with multiple argument into a series of func each taking a single
argument.
function curryAdd(a){
   return function a(b){
      return function b(c){
        return a+b+c
       }
   }
}

console.log(curryAdd(1)(2)(3))


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

# interviewPreparation-2025

SYSTEM DESIGN QUESTION:-
  Stangler Design Pattern:- break into small parts and ship from monolathic to microservices 
  ex:- Restraunt : planing to create new kitchen and start cooking it start from single item once that ship well then gradually other items will 
  be cook there.
