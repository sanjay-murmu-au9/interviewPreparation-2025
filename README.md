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

# interviewPreparation-2025

SYSTEM DESIGN QUESTION:-
  Stangler Design Pattern:- break into small parts and ship from monolathic to microservices 
  ex:- Restraunt : planing to create new kitchen and start cooking it start from single item once that ship well then gradually other items will 
  be cook there.
