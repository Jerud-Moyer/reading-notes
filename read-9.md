## SQL tutorial (continued)
    - excellent practice with joins and stuff.

## database normalization (explained in simple English)
- introduction to database noramlization
    - a process used to organize a database into tables and columns
    - by limiting a table to one purpose you reduce the number of duplicate data in your database
- reasons for DB normalization
    - minimize duplicate data
    - avoid data modification issues
    - simplify queries
- data duplication and modification issues
    - it increases storage and decreases performance
    - it becomes more difficult to mauntain data changes
        - insert anomaly
        - update anomaly
        - deletion anomaly
- search and sort issues
- definition of DB normailization
    - 3 common forms
        - First Normal Form – The information is stored in a relational table with each column containing atomic values. There are no repeating groups of columns.
        - Second Normal Form – The table is in first normal form and all the columns depend on the table’s primary key.
        - Third Normal Form – the table is in second normal form and all of its columns are not transitively dependent on the primary key
## visual representation of SQL joins
- inner join
    - the most common join. it will gatt=her all the records that match fron 2 tables
- left join
    - all the records from left table and any matching from right
- right join
    - like above but opposite
- outer join
    - OR FULL join all from both!
- left excluding
    - all records from left *withouT* matches on right
- right excluding
    - see above
- outer excluding
    - all non matching from both
 - very helpfull guide https://www.codeproject.com/Articles/33052/Visual-Representation-of-SQL-Joins   


