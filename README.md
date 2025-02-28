Nodejs
1. what is nodejs
Its a javascript run time, run outside the browser build on v8 chrome engine, non-blocking, event based architucture.

 2. What is closure?
    :- Function remember outer scope varaible event the execution has completed, even outer func is excuted.
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
    count()
    
    count()




# interviewPreparation-2025

SYSTEM DESIGN QUESTION:-
  Stangler Design Pattern:- break into small parts and ship from monolathic to microservices 
  ex:- Restraunt : planing to create new kitchen and start cooking it start from single item once that ship well then gradually other items will 
  be cook there.
