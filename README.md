Hlw from SQL
// AND OR
SELECT column_name(s)
FROM table_name
WHERE condition
AND| OR condtion

//ALTER TABLE
ALTER TABLE table_name
ADD column_name datatype

or
ALTER TABLE table_name
DROP COLUMN column_name

AS(alias)
SELECT column_name AS column_alias
FROM table_name
 //or
 SELECT column_name
 FROM table_name AS table_alias
 
 
 
 // BETWEEN
 SELECT *
 FROM table_name
 WHERE column_name
 BETWEEN val1 AND val2 // salary 45,30
 
 // create database
 CREATE DATABASE data_base_name;
 
 //table
 CREATE TABLE table_name(
    column_name1 data_type,
    column_name2 data_type,
    ...
 )
 
 //create Index
 CREATE INDEX index_name ON table_name (column_name)
 CREATE UNIQUE INDEX index_name ON table_name (column_name,DESC)
 
 // DELETE
 DELETE FROM table_name
 WHERE some_column=some_value;
 
 or
 DELETE FROM table_name
 (Note: delete the entire table!!)
 
 DELETE * FROM table_name
 (Note: Delete the entire table!!)
 
 // DROP DATABSE
 DROP DATABASE database_name
 
 // drop Index
 DROP INDEX table_name.index_name (SQL SERVER)
 
 //drop table
 DROP TABLE table_name
 
 // EXISTS
 IF EXISTS (SELECT * FROM table_name WHERE id = ?)
 BEGIN
 -- do what needs to be done if exits
 END
 ELSE
 BEGIN
  -- do what need to be done if not
 END
 
 // GROUP BY aggreagte 
 SELECT column_name, aggregate_function(column_name)
 FROM table_name
 WHERE column_name operator value
 GROUP BY column_name
 HAVING aggregate_function(column_name) operator value

