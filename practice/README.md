# Introduction to Databases & SQL

### Practice

**Exercise 0: DATABASE QUESTIONS**
  
- What role does a database play in a fullstack web application?
- What is Postgres?
- What is SQL?
  
**Exercise 1: SET UP**
- If you have not already, set up Postgres by following the [Postgres setup instructions](https://github.com/The-Marcy-Lab-School/postgres-setup).

**Exercise 2: ACCESS COMMAND LINE**

- Go to the command line and connect to your database by running the command `psql`.
- Now you are connected to PostgreSQL!
- To exit from PostgreSQL, use `control d`.
- Run the command `\l` within your `psql` command line.
- **What is does the `l` command output?**

**Exercise 3: CREATE DATABASE AND CONNECT**
- Create a database called `marcy` by running the command `CREATE DATABASE marcy;`
  - **NOTE** the semi-colon is important for ending the execution of this command! Makes sure to include it.
- You have successfully created a database if your `psql` command line outputs `CREATE DATABASE`.
  - If it didn't, you might just need to enter a `;` to complete the command.
- Next, connect to your database by running the command `\c marcy`. Successfully connecting to your database will output `You are now connected to database "marcy" as user "[your username]"`.

**Exercise 4: CREATE TABLES**

- Created a table called `lessons` by running the command
`CREATE TABLE lessons(id SERIAL PRIMARY KEY, title TEXT NOT NULL, instructor TEXT NOT NULL);`
- You should see `CREATE TABLE` if this was successful
- **Based on this command, what do you imagine the rows and columns of your lessons table to be?**
- To see a description of the table you just created, run the command `\d lessons`.

**Exercise 5: BASIC QUERIES - POPULATE TABLES**

- Give your table some data. Follow the Postgres documentation for [populating tables with rows](https://www.postgresql.org/docs/12/tutorial-populate.html).
- Run the command `INSERT INTO lessons VALUES('data structures', 'carmen');`
- We only need to provide the lesson `title` and `instructor`. Why don't we need to provide the `id`?
- Input 5 more lessons using the same syntax for different lessons and instructors.

**Exercise 6: BASIC QUERIES - SELECT DATA**

- Run the command `SELECT * FROM lessons`. **What does this command do?**
- Run other SELECT commands and use the [Querying a Table Documentation as a reference](https://www.postgresql.org/docs/12/tutorial-select.html)
- **Write a reflection on the pros and cons of inputting and accessing data using the `INSERT` and `SELECT` commands.**

**Exercise 7: MORE BASIC QUERIES**

Get all data from the `title` and `instructor` columns in the `lessons` table:
```sql
SELECT title, instructor FROM lessons;
```

Get the title of each lesson, but only from the rows where the value in the `instructor` column is `'Ben'`:

```sql
SELECT title FROM lessons WHERE instructor='Ben';
```

Same as above, but now we are also including rows where the value in the `instructor` column is `'Gonzalo'`:

```sql
SELECT title FROM lessons WHERE instructor='Ben' OR instructor='Gonzalo';
```

Renaming queries with `AS`:

```sql
SELECT title AS "Course Title" FROM lessons;
```

Counting the number of rows in the `lessons` table:

```sql
SELECT COUNT(*) FROM lessons
```

Counting the number of lessons taught by `'Ben'`:

```sql
SELECT COUNT(*) FROM lessons WHERE instructor='Ben'
```

Collapsing columns with `GROUP BY`:

```sql
SELECT COUNT(*), instructor FROM lessons WHERE instructor='ben' GROUP BY instructor;
```

Update existing rows

```sql
UPDATE lessons SET instructor = 'Gonzalo' WHERE title = 'Data Structures';
```

Delete existing rows

```sql
DELETE FROM lessons WHERE title = 'Data Structures';
```


- http://pgexercises.com provides listings of simple SQL Queries. Keep your documentation handy.
- Visit the [exercises](https://pgexercises.com/questions/basic/).
- Solutions are embedded in the exercise app after you complete a prompt.
