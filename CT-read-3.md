### Inside a Computer
#### video
- https://edu.gcfglobal.org/en/computerbasics/inside-a-computer/1/
- some basics about the construction of a computer
- Motherboard
    - the main circuit board
        - connects directly or indirectly to every part of the computer'
- CPU/Processor
    - Central Processing Unit
    - located on the motherboard
- RAM
    - Random Access Memory
    - the system's short term memory
- Hard Drive
    - long term storage
- Power Supply Unit
- Expansion Cards
    - video card
    - sound card
    - network card
    - bluetooth card
## Postgres
### postgres INSERT
- INSERT INTO table_name(column1, column2)
  VALUE (value1, value2);
- RETURNING clause
    - optionanal clause that returns the information of the inserted row
- INSERT INTO links (url, name)
VALUES('https://www.postgresqltutorial.com','PostgreSQL Tutorial');
- if you want to insert a string that contains a single quote (') such as O'Reilly Media, you have to use an additional single quote (') to escape it
- inserting a date value
    -  INSERT INTO links (url, name, last_update)
VALUES('https://www.google.com','Google','2013-06-01');
- getting the last insert id
    - INSERT INTO links (url, name)
    VALUES('http://www.postgresql.org','PostgreSQL') 
    RETURNING id;
### postgres SELECT
- The SELECT statement is one of the most complex statements in PostgreSQL. It has many clauses that you can use to form a flexible query.
- SELECT clauses
    - Select distinct rows using DISTINCT operator.
    - Filter rows using WHERE clause
    - Select a subset of rows from a table using LIMIT or FETCH clause
    - Group rows into groups using GROUP BY clause
    - Filter groups using HAVING clause
    - Join with other tables using joins such as INNER JOIN, LEFT JOIN, FULL OUTER JOIN, CROSS JOIN clauses
    - Perform set operations using UNION, INTERSECT and EXCEPT
- First specify a select list that can be a column or a list of columns from a table
- second specify the name of the table from which to select
- SELECT
   -  first_name,
   -  last_name,
   -  email
- FROM
    - customer;
### postgres UPDATE
- UPDATE allows yout to modify data in a table
- UPDATE table_name
- SET column1 = value1,
    - column2 = value2,
    - ...
- WHERE condition;
### postgres DELETE
- DELETE FROM table_name
- WHERE condition;




    




