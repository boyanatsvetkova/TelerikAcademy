#Database Systems – Overview
1.	What database models do you know?
  *	Hierarchical (tree)
  *	Graph
  *	Relational
  *	Object-oriented

2.	Which are the main functions performed by a Relational Database Management System (RDBMS)?
  *	Creating, altering, deleting tables and the relationships between them
  *	Adding, changing, deleting, searching and retrieving of data stored in the tables
  *	Support of the SQL language
  *	Transaction management
  
3.	Define what is "table" in database terms.
    *	Database table is arranged in rows and columns where specific data are stored. All rows of the table have the same structure whereas columns have specific name and type supported. 
    
4.	Explain the difference between a primary and a foreign key.
  *	**Primary key** of a table uniquely identifies its row. In order to achieve data integrity, in other words to avoid repeating data, each row in the table must be assigned unique primary key.
  *	**Foreign key** is used to make the relationship between two tables. The foreign key of the child table points to the primary key of the parent table. The primary key of the parent table corresponds to the foreign key of the child table. Data are retrieved from the parent table and filled as information part of the child table when query statements are executed. Foreign key constraint ensures data integrity of the database. Duplication and incorrectness of data are avoided.
  
5.	Explain the different kinds of relationships between tables in relational databases.
  *	**One – to – one relationship** – each row in one table is linked to 1 and only 1 other row in another table. For example, one cardholder is entitled to only one credit card. 
  *	**One – to – many relationship** – each row in the related to table can be related to many rows in the relating table. This allows frequently used information to be saved only once in a table and referenced many times in all other tables. For example, a user of a website can post as many comments as he or she wants. Yet, each comment made can be posted by only one user.
  *	**Many – to – many relationship** – one or more rows in a table can be related to 0, 1 or many rows in another table. For example, a student can attend a multiple classes in the university as well as a class can be attended by multiple students.
  
6.	When is a certain database schema normalized? What are the advantages of normalized databases?
  *	When separate tables for each group of related data are created and each row is identified with a unique column or set of columns (the primary key).
  *	When subsets of data that apply to multiple rows of a table are removed and placed in separate tables. Relationships between these new tables and their predecessors are created through the use of foreign keys.
  *	When columns that are not dependent upon the primary key are removed.
  *	Advantages: 
    1.	No redundant data
    2.	Queries on data run faster because there is less data to search through 
    3.	No data duplication which leads to better data integrity and less risk of mistakes
    4.	Less chance of storing two or more different copies of the data
    5.	One change can be made which can instantly be cascaded across any related records. 
    
7.	  What are database integrity constraints and when are they used?
  *	Specific rules on the database which must be followed when inserting, deleting or updating data.
  
8.	Point out the pros and cons of using indexes in a database.
  *	Indeces make searching through data faster
  *	Indeces should be used when searching through enormous data quantity because they take up too much store space which use should be justified
  *	When changing data indeces should also be updated. Additional resources are need to keep indices with up-to-date information
  
9.	What's the main purpose of the SQL language?
  *	Main tool for communication with the database
  
10.	What are transactions used for? Give an example.
  * A transaction is the propagation of one or more changes to the database. Transactions are atomic which means that all operations within the work unit are completed successfully otherwise the transaction is aborted and the previous operations are rolled back to their former state; consistent – the database properly changes states upon successfully committed transaction; isolated – enables transactions to operate independently of or transparent to each other; durable – ensures that the result or the effect of a committed transaction persists in the case of a system failure.
For example, if a person wants to withdraw money from his/her bank account and suddenly the power goes off during the withdrawal process the transaction is rolled back to its initial state so that person can have the chance to withdraw it again. Instead of being put in the situation when the money is said to be withdrawn but in the same time the person did have the chance to take it from the machine as the power went off.

11.	What is a NoSQL database?
  *	NoSQL are non-relational database. There are no relationships between the elements of the database. There is no data consistency. No columns and their corresponding types and rules exist.
  
12.	Explain the classical non-relational data models.
  *	**Document model** – data are stored across set of documents in JSON string format
  *	**Key-value model** – a data storage paradigm designed for storing, retrieving, and managing associative arrays, a data structure more commonly known today as a dictionary or hash.
  *	**Hierarchical key-value model** – a data model in which the data is organized into a tree-like structure. The data is stored as records which are connected to one another through links. A record is a collection of fields, with each field containing only one value.
  *	**Wide – column model** – stores data in records with an ability to hold very large numbers of dynamic columns. Since the column names as well as the record keys are not fixed, and since a record can have billions of columns, wide column stores can be seen as two-dimensional key-value stores.
  * **Object model** – a database management system in which information is represented in the form of objects as used in object-oriented programming. 

13.	Give few examples of NoSQL databases and their pros and cons.
  *	**MongoDB** 
    1.	data size is typically higher
    2.	less flexibity with querying
    3.	no support for transactions
    4.	schema-less (ideal for flexible schema)
    5.	ease of scale-out
    6.	free and can run on Linux
  *	**Cassandra**
    1.	Better performance for write heavy operations
    2.	Data model and inherent indexing on timestamp are useful when a lot of sequencing of data like wall updates on Facebook is needed
  *	**Redis**
    1.	Stores data in a variety of formats: list, array, sets and sorted sets
    2.	Blocking reads -- will sit and wait until another process writes data to the cache
    3.	Partitions data across multiple redis instances
    4.	Mass insertion of data to prime a cache
    5.	Super complex to configure -- requires consideration of data size to configure well
    6.	Lots of server administration for monitoring and partitioning and balancing
  *	**CouchDB**
    1.	simplicity, you can store any JSON data
    2.	thanks to map/reduce, querying data is somewhat separated from the data itself. This means that you can index deeply within your data, and on whether or not something exists, and across types, without paying a significant penalty
    3.	arbitrary queries are expensive. To do a query that you haven't created a view for, you need to create a temporary view
    4.	there's a bit of extra space overhead with CouchDB compared to most alternatives.







