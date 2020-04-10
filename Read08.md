# SQL :keyboard:

**Reading**

1. [Complete SQLBolt (Intro, Lessons 1-4, 13-18)](https://sqlbolt.com/)
1. Practice SQL on [W3 Schools](https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_all) - This resource has sample databases you can use to practice writing SQL queries.

**Additional Resources**

1. [A Primer on SQL](https://openlibra.com/en/book/a-primer-on-sql-3rd-edition) - Click the blue Download button
1. [SQL Cheat Sheet](http://www.cheat-sheets.org/sites/sql.su/)
1. SQL Playground

**Importanat Links**

- [SQL Syntax Cheatsheet](https://codefellows.github.io/code-301-guide/curriculum/class-08/cheatsheets/sql)
- [PostgreSQL Shell Cheatsheet](https://codefellows.github.io/code-301-guide/curriculum/class-08/cheatsheets/postgres-shell)
- [PostgreSQL Docs](https://www.postgresql.org/docs/)
- [Heroku Postgres Docs](https://devcenter.heroku.com/articles/heroku-postgresql)

### What is SQL? :interrobang:

- **Structured Query Language**
- is a **language** designed to allow both technical and non-technical users **query**, **manipulate**, and **transform data** from a relational database.
- due to its _simplicity_, SQL databases provide _safe_ and _scalable storage_ for millions of websites and mobile applications.

```There are many popular SQL databases including

1. SQLite
2. MySQL
3. Postgres
4. Oracle
5. Microsoft SQL Server.

All of them support the common SQL language standard, but each implementation can differ in the additional features and storage types it supports.
```

**getting the information from DataBase could take miliseconds but from the cloud it will take second**
**we can save the info from the cloud at the DB(DataBase) :card_index_dividers: to use it quieckly**

### SQL Lesson 1: SELECT queries 101 :date:

- To **retrieve data** from a SQL database, we need to write **SELECT** statements
  - **select statement** refere to **queries**
  - **A query** just a **statement** which declares:
    - **what** data we are looking for
    - **where** to find it in the database
    - **how** to transform it before it is returned._query has a specific syntax._

`SELECT * FROM mytable;` This query, in particular, is really **useful** because it's a **simple** way to **inspect** a **table** by **dumping all the data at once**.

```SELECT * FROM movies;
 SELECT title FROM movies;
SELECT director FROM movies;
SELECT title, director FROM movies;
SELECT title, year FROM movies;
```

### SQL Lesson 2: Queries with constraints(restrictions) (Pt. 1) :paperclip:

- use a **WHERE** clause in the query
  - The clause is applied to **each row** of data by **checking specific column** **values** to determine whether it should be included in the results or not.
- complex clauses can be constructed by joining numerous logical keywords like:

  - **AND**
  - **OR**

    ![SQL-operators](img/SQL-operators.png)

- **writing clauses to constrain the set of rows returned**:

  - **making the results more manageable to understand**
  - allows the _query_ to _run faster_ due to the reduction in unnecessary data being returned.

    ```SELECT title, year FROM movies
      WHERE year BETWEEN 2000 AND 2010;
      SELECT title, year FROM movies
      WHERE year < 2000 OR year > 2010;
    ```

### SQL Lesson 3: Queries with constraints (Pt. 2) :paperclip:

When writing **WHERE** clauses with columns containing text data,
**SQL** supports **operators** to do:

1. case-insensitive string comparison.
1. wildcard pattern matching.

We show a few common **text-data specific operators**

![text-data specific operators](img/SQL-operators1.png)

**full-text search** is best left to dedicated **libraries** like [Apache Lucene](https://lucene.apache.org/) or [Sphinx](http://sphinxsearch.com/). which designed specifically to do full text search.

```SELECT title, director FROM movies
WHERE title LIKE "Toy Story%";

SELECT  title director FROM movies
WHERE director LIKE "John Lasseter";

SELECT  title director FROM movies
WHERE director NOT LIKE "John Lasseter";

SELECT  title director FROM movies
WHERE title  LIKE "WALL%";
```

### SQL Lesson 4: Filtering and sorting Query results :card_file_box:

To **discard** rows that have a **duplicate column value** by using the **DISTINCT (special)** keyword.
way to **sort** results by a given column in ascending or descending order using the **ORDER BY** clause.
used with:

- **LIMIT** will reduce the number of rows to return
- **OFFSET** will specify where to begin counting the number rows from.
  `LIMIT and OFFSET are applied relative to the other parts of a query, they are generally done last after the other clauses have been applied`

```
directors of movies (alphabetically)
SELECT DISTINCT director FROM movies ORDER BY director ASC;

last four movies released (ordered from most recent to least)
SELECT title, year FROM movies ORDER BY year DESC LIMIT 4;

List the first five Pixar movies sorted alphabetically
SELECT title FROM movies ORDER BY title ASC LIMIT 5;

List the next five Pixar movies sorted alphabetically
SELECT title FROM movies ORDER BY title ASC LIMIT 5 OFFSET 5;

```

## REVIEW

```
SELECT query
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC
LIMIT num_limit OFFSET num_offset;
```

**EXAMPLES**

```
Order all the cities in the United States by their latitude from north to south.
SELECT city, latitude FROM north_american_cities WHERE country ="United States" ORDER BY latitude DESC;

List all the cities west of Chicago, ordered from west to east
SELECT city, longitude FROM north_american_cities WHERE longitude < -87.629798 ORDER BY longitude ASC;

List the two largest cities in Mexico (by population)
SELECT city, population FROM north_american_cities WHERE country LIKE "Mexico" ORDER BY population DESC LIMIT 2;

List the third and fourth largest cities (by population) in the United States and their population
SELECT city, population FROM north_american_cities
WHERE country LIKE "United States"
ORDER BY population DESC
LIMIT 2 OFFSET 2;
```

### SQL Lesson 6: Multi-table queries with JOINs :chart_with_upwards_trend:

we've been working with a **single** **table**, but entity data is often broken down into pieces and stored across multiple **orthogonal** **tables** using a process known as **normalization**
`Database normalization useful because it minimizes duplicate data in any single table, and allows for data in the database to grow independently of each other`

1. **Tables** that share information about a **single entity** need to have a **primary key** that identifies that entity uniquely across the database.
   - One common primary key type is **an auto-incrementing integer** (because they are space efficient)
     - it can also be a **string**
     - **hashed value**, so long as it is unique.

**JOIN** clause in a query:
to combine **row** data across **two** **separate** **tables** using this **unique key**.

1. The first of the **joins** is the **INNER JOIN**.

   - **INNER JOIN** is a **process** that **matches** **rows** from the **first table** and the **second table** which have the **same key** (as defined by the ON constraint) to **create** a result **row** with the **combined** **columns** from **both tables**.

   ```
   Find the domestic and international sales for each movie
   SELECT title, domestic_sales, International_sales FROM movies JOIN Boxoffice ON movies.id =  boxoffice.movie_id;

   Show the sales numbers for each movie that did better internationally rather than domestically
   SELECT title, domestic_sales, international_sales
   FROM movies
   JOIN boxoffice
    ON movies.id = boxoffice.movie_id
   WHERE international_sales > domestic_sales;

   List all the movies by their ratings in descending order
   SELECT title, Rating FROM movies
   JOIN boxoffice ON movies.id=boxoffice.movie_id
   WHERE rating ORDER BY rating DESC;
   ```

### SQL Lesson 7: OUTER JOINs :round_pushpin:

**INNER JOIN** is **not sufficient** because the resulting table only **contains** data that **belongs in both** of the tables.

1. two tables have **asymmetric** data then we would have to use:
   (to ensure that the data you need is **not left out of the results**.)

   - **LEFT JOIN**
   - **RIGHT JOIN**
   - **FULL JOIN**

TABLE A & TABLE B :

1. **LEFT JOIN** includes **rows** from **A** **regardless** of whether a **matching** **row** is found in **B**.
1. **RIGHT JOIN** is the same, but reversed, keeping **rows** in **B** **regardless** of whether a **match** is found in **A**.
1. **FULL JOIN** **rows** from **both** tables are **kept**, **regardless** of whether a **matching** row exists in the **other** table.

```
Find the list of all buildings that have employees
SELECT DISTINCT building FROM Employees ;

List all buildings and the distinct employee roles in each building (including empty buildings)
SELECT DISTINCT building_name, role
FROM buildings
LEFT JOIN employees
ON building_name = building;
```

### SQL Lesson 8: A short note on NULLs :no_entry_sign:

good to **reduce** the possibility of **NULL** values in **databases** because they require **special** attention when :

1. **constructing** queries.
1. **constraints** (certain functions behave differently with null values)
1. when **processing** the results.

An **alternative** to **NULL** values in **database** is to have **data-type appropriate default values**

1.  **0** for **numerical** data
1.  **empty strings** for **text data**

Test a **column** for **NULL** values in a **WHERE** clause by using either the:

1. **IS NULL**
1. **IS NOT NULL** constraint.

```
Find the name and role of all employees who have not been assigned to a building
SELECT DISTINCT Name, role FROM Employees WHERE Building IS NULL;

Find the names of the buildings that hold no employees
SELECT DISTINCT building_name FROM buildings LEFT JOIN employees ON building_name = building WHERE role IS NULL;
```

### SQL Lesson 9: Queries with expressions :cowboy_hat_face:

### SQL Lesson 10: Queries with aggregates (Pt. 1) :nerd_face:

### SQL Lesson 11: Queries with aggregates (Pt. 2) :nerd_face:

### SQL Lesson 12: Order of execution of a Query :fountain_pen:

### SQL Lesson 13: Inserting rows :bar_chart:

### SQL Lesson 14: Updating rows :bookmark_tabs:

### SQL Lesson 15: Deleting rows :no_entry:

### SQL Lesson 16: Creating tables :card_file_box:

### SQL Lesson 17: Altering tables :bar_chart:

### SQL Lesson 18: Dropping tables :bar_chart:

**SQL**
`terminal commands (psql-f schema.sql -d demo)`
its a language not database, **database** contain recodrds of data stored in some place, and use english language sentences to _talk_ and acess the _database_
**Query language**

- query is question (request the data or info)
- database query:
  - select query : retiev data
  - action query : additional operations (insertion, updating and deleting)

**postgress**
_on the terminal_

1. **win -> sudo service postgresql start**
1. **pgstart**

**POSTGRES**
is a server running on machine and holds database
it has address can be connect to
to connect to postgress:
**go to terminal and**

1. already done with (pgstart) point
1. **psql**
1. **CREATE DATABASE demo;** (demo the name of the database)
1. **\l** list of the databse
1. connect to the created database **\c demo**
1. **\d** tables in database
1. **CREATE TABLE people (** table name is people
1. start to build it **person_id int,**
1. **first_name varchar(255),** max char 255
1. **last_name varchar(255)** max char 255
1. **);**
1. **INSERT INTO people VALUES ('1', 'Bebo', '3asal');**

### Schema collection of database objects with one database_username
