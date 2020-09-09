## PostgreSQL joins tutorial
- https://www.postgresqltutorial.com/postgresql-joins/
- joins are used to combine columns from different tables
- inner join gets common data
- left outer join gets all from  table a and matching rows from the right
- right is reversed
- full join will get all
- full outer will only get 'unique' lines from each side
## one to one (data model)
- In systems analysis, a one-to-one relationship is a type of cardinality that refers to the relationship between two entities (see also entity–relationship model) A and B in which one element of A may only be linked to one element of B, and vice versa.
- In a relational database, a one-to-one relationship exists when one row in a table may be linked with only one row in another table and vice versa.

## One-to-many(data model)
- In systems analysis, a one-to-many relationship is a type of cardinality that refers to the relationship between two entities (see also entity–relationship model) A and B in which an element of A may be linked to many elements of B, but a member of B is linked to only one element of A. For instance, think of A as books, and B as pages. A book can have many pages, but a page can only be in one book.
- In a relational database, a one-to-many relationship exists when one row in table A may be linked with many rows in table B, but one row in table B is linked to only one row in table A.

## Many-to-many (data model)
- In systems analysis, a many-to-many relationship is a type of cardinality that refers to the relationship between two entities[1] A and B in which A may contain a parent instance for which there are many children in B and vice versa.
- In a relational database management system, such relationships are usually implemented by means of an associative table (also known as join table, junction table or cross-reference table), say, AB with two one-to-many relationships A -> AB and B -> AB. In this case the logical primary key for AB is formed from the two foreign keys (i.e. copies of the primary keys of A and B)
