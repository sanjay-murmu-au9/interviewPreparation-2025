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


Nodejs
1. what is nodejs
Its a cross platform javascript run time, run outside the browser build on v8 chrome engine, non-blocking, event based architucture. opensourch.

2. How is Node.js different from JavaScript in the browser?
:- Js:- run in browser, Can access: access to local storage,DOM & uses: UI intraction
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
   console.log(`Server is listening on ${Port}`)
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
 callBack :- func pass as arguments eg:- fs.readFile(file,callback)
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

# interviewPreparation-2025

SYSTEM DESIGN QUESTION:-
  Stangler Design Pattern:- break into small parts and ship from monolathic to microservices 
  ex:- Restraunt : planing to create new kitchen and start cooking it start from single item once that ship well then gradually other items will 
  be cook there.
