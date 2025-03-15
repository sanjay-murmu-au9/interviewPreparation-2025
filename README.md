# interviewPreparation-2025

SYSTEM DESIGN QUESTION:-
  Stangler Design Pattern:- break into small parts and ship from monolathic to microservices 
  ex:- Restraunt : planing to create new kitchen and start cooking it start from single item once that ship well then gradually other items will 
  be cook there.

#https://medium.com/double-pointer/top-seven-interview-questions-on-search-indexes-for-software-engineering-interviews-5256b703c616
# Search Indexes
 Indexing:- Its a Data strucuture that help in speed of data retriving in most optimised way in database, search engine;
or 
(reduces the time complexity of looksup instead of full scan; seach index allow you to get effecient retrival of record; ensure scalibilty in application with large dataset)

Why it is Important?
  :- Workinging with large E-commerce platform and product catalog present millions for items withoud finding a product by name would scan intire tables
which would be inefficient. search index provide faster looksup and enhences user experiece by deliverying quick reasult;


# How Does a B-Tree Index Work(Regular Index)?
Its one of the common used indexes in datasets to keep search operation fast;
1. in store data in balance tree structure that allow logarithmic time complexity (Olog n ) data structure 
2. when search for a key its search from root to the  leaf.which make efficient for large datasets;

# Explain the Differences Between a Full-Text Index and a Regular Index
:- FTIndex:- is used for text heavy database such as document storage system, it tokenize the text adnd enable key based search & also has advance feature like relevance ranking
and partial keyword match; eg long form of blog app; 
:- Regular search Index work well for strucutred data and exact match

# When Would You Use a Hash Index, and What Are Its Limitations?
:- used for quick lookups based on exact matched keyword; however it doesn't range queries and partial match which is good B tres indexes;

How Would You Handle Index Maintenance in a System with Frequent Writes?
:- Indexes maintaince could be expensive for frequently write-heavy app; and can slow down for insertion 
so I would consider reduce the no of indexes or looks for the indexes strategy that support fast write such as partition indexes Or
differing indexes updates in batch jobs;

# How Do Inverted Indexes Work in Search Engines?
























