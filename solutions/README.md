# Introduction to Databases & SQL

### Solutions

**Exercise 0:**
* A database secures and manages the data for an application. Whenever the client requests data from the backend, the server application can query the database for the data and then send it to the client.
* Postgres is a relational database management system that organizes data in tables
* SQL is a language for issuing commands to create, reade, update, or delete data from a relational database like Postgres.

**Exercise 2:**
The command `l` (from the `psql` command line) outputs a list view of databases. **NOTE** The only user of your database is current you. But if you were working at a company with multiple staff members, then it would be common to see several database owners.

**Exercise 3:**
The projects table will have an id row, name row, and password row. There are also some contraints that require the primary key to be a number (that's what SERIAL stands for) and requires the name and partners to text that is not null.

**Exercise 6:**
_Reflections may vary_

Writing commands using SQL is pretty clear. However, writing indivudal commands for inputting individual pieces of data can be tedious.
