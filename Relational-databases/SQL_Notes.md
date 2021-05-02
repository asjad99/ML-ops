
#### Topics: 

1. Data Modeling: A brief Overview
2. Basic SQL 
3. SQL Joins 
4. SQL Aggregations
5. SQL data Cleaning
6. SQL Indexing and Performance Tuning 


-----

### Introduction 

DataBase: A collection of tables that share connected data stored in a computer. 

#### Entity Relationship Diagrams

An entity relationship diagram (ERD) is a common way to view data in a database. Below is the ERD for the database we will use from Parch & Posey. These diagrams help you visualize the data you are analyzing including:


1. The names of the tables.
2. The columns in each table.
3. The way the tables work together.

You can think of each of the boxes below as a spreadsheet.

![](https://video.udacity-data.com/topher/2017/August/59821d7d_screen-shot-2017-08-02-at-11.14.25-am/screen-shot-2017-08-02-at-11.14.25-am.png)

### What to Notice

In the Parch & Posey database there are five tables (essentially 5 spreadsheets):


1. web_events
2. accounts
3. orders
4. sales_reps
5. region

You can think of each of these tables as an individual spreadsheet. Then the columns in each spreadsheet are listed below the table name. For example, the region table has two columns: `id` and `name`. Alternatively the web_events table has four columns.

![](https://video.udacity-data.com/topher/2017/August/59852269_screen-shot-2017-08-04-at-6.41.07-pm/screen-shot-2017-08-04-at-6.41.07-pm.png)


The "crow's foot" that connects the tables together shows us how the columns in one table relate to the columns in another table. In this first lesson, you will be learning the basics of how to work with SQL to interact with a single table. In the next lesson, you will learn more about why these connections are so important for working with SQL and relational databases.


|                                                                                                      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                         | Example                                                                                                                                                                                                                                                                                                                                                                             |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| SELECT                                                                                               | indicates which column(s) you want to be given the data for.                                                                                                                                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                                                                                                                                                                     |
| FROM                                                                                                 | specifies from which table(s) you want to select the columns. Notice the columns need to exist in this table.                                                                                                                                                                                                                                                                                                                                                       |                                                                                                                                                                                                                                                                                                                                                                                     |
| LIMIT                                                                                                | statement is useful when you want to see just the first few rows of a table. The LIMIT command is always the very last part of a query.                                                                                                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                                                                                                                                                                     |
| ORDER BY                                                                                             | statement allows us to sort our results using the data in any column. `DESC` can be added after the column in your ORDER BY statement to sort in descending order                                                                                                                                                                                                                                                                                                   | SELECT id, account_id, occurred_at<br>FROM orders<br>ORDER BY occurred_at<br>LIMIT 15;<br><br>In ORDER BY if we specify multiple values. e.g <br><br>SELECT account_id, total_amt_usd<br>FROM orders<br>ORDER BY total_amt_usd DESC, account_id<br><br>this means if there are multiple enteries containing same ‘total_amt_usd’. then the corresponding account_id will be sorted. |
| WHERE                                                                                                | we can display subsets of tables based on conditions that must be met. You can also think of the WHERE command as filtering the data.                                                                                                                                                                                                                                                                                                                               | SELECT  id,account_id,total_amt_usd<br>FROM orders<br>WHERE account_id = 4251<br>ORDER BY account_id, total_amt_usd DESC<br><br><br>SELECT name, website, primary_poc<br>FROM accounts<br>WHERE name = 'Exxon Mobil';                                                                                                                                                               |
| Basic Arithmatic                                                                                     | Compute % of sales                                                                                                                                                                                                                                                                                                                                                                                                                                                  | SELECT id, account_id, <br>   poster_amt_usd/(standard_amt_usd + gloss_amt_usd + poster_amt_usd) AS post_per<br>FROM orders<br>LIMIT 10;                                                                                                                                                                                                                                            |
| 1. LIKE                                                                                              | - This allows you to perform operations similar to using WHERE and `=`, but for cases when you might not know exactly what you are looking for.<br>- The LIKE operator is extremely useful for working with text. <br>- You will use LIKE within a WHERE clause. The LIKE operator is frequently used with `%`. The `%` tells us that we might want any number of characters leading up to a particular set of characters or following a certain set of characters, | SELECT *<br>FROM accounts<br>WHERE name LIKE '%s’<br><br>companies whose name end with s.                                                                                                                                                                                                                                                                                           |
| 1. IN                                                                                                | This allows you to perform operations similar to using WHERE and `=`, but for more than one condition.                                                                                                                                                                                                                                                                                                                                                              | SELECT name, primary_poc, sales_rep_id`<br>FROM accounts`<br>WHERE name IN ('Walmart', 'Target', 'Nordstrom');<br><br>SELECT *<br>FROM web_events<br>WHERE channel IN ('organic', 'adwords')                                                                                                                                                                                        |
| NOT                                                                                                  | This is used with IN and LIKE to select all of the rows NOT LIKE or NOT IN a certain condition.<br><br>The NOT operator is an extremely useful operator for working with the previous two operators we introduced: IN and LIKE. By specifying NOT LIKE or NOT IN, we can grab all of the rows that do not meet a particular criteria.                                                                                                                               | `SELECT` ```name``, primary_poc, sales_rep_id`<br>`FROM` `accounts`<br>`WHERE` ```name` ```NOT` ```IN` `('Walmart', 'Target', 'Nordstrom');`<br>`SELECT` `*`<br>`FROM` `web_events`<br>`WHERE` `channel` `NOT` ```IN` `('organic', 'adwords');`                                                                                                                                     |
| AND & BETWEEN These allow you to combine operations where all combined conditions must be true.      | The AND operator is used within a WHERE statement to consider more than one logical clause at a time                                                                                                                                                                                                                                                                                                                                                                | `SELECT` `*`<br>`FROM` `orders`<br>`WHERE` `standard_qty > 1000` `AND` `poster_qty = 0` `AND` `gloss_qty = 0;`<br><br>`SELECT` ```name`<br>`FROM` `accounts`<br>`WHERE` ```name` ```NOT` ```LIKE` `'C%'` `AND` ```name` ```LIKE` `'%s';`                                                                                                                                            |
| OR This allows you to combine operations where at least one of the combined conditions must be true. |                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                                                          ----------                                                                                                                                                                                                                                                                                                                           |


### Tips: 

- it is common and best practice to capitalize all SQL commands, like SELECT and FROM, and keep everything else in your query lower case.
- It is common to use underscores and avoid spaces in column names.
- SQL queries ignore spaces, so you can add as many spaces and blank lines between code as you want, and the queries are the same. 
-  It is considered best practice to put a semicolon at the end of each statement, which also allows you to run multiple queries at once if your environment allows this.
- SELECT is first clause, LIMIT is last, 


----------

    Write a query that displays the order ID, account ID, and total dollar amount for all the orders,
    sorted first by the account ID (in ascending order), and then by the total dollar amount (in descending order).


    SELECT  id,account_id,total_amt_usd
    FROM orders
    ORDER BY account_id, total_amt_usd DESC

Note: switching account_id and total_amt_usd DESC returns different results. 


### Summary


| Statement | How to Use It               | Other Details                                         |
| --------- | --------------------------- | ----------------------------------------------------- |
| SELECT    | SELECT Col1, Col2, ...      | Provide the columns you want                          |
| FROM      | FROM Table                  | Provide the table where the columns exist             |
| LIMIT     | LIMIT 10                    | Limits based number of rows returned                  |
| ORDER BY  | ORDER BY Col                | Orders table based on the column. Used with DESC.     |
| WHERE     | WHERE Col > 5               | A conditional statement to filter your results        |
| LIKE      | WHERE Col LIKE '%me%'       | Only pulls rows where column has 'me' within the text |
| IN        | WHERE Col IN ('Y', 'N')     | A filter for only rows with column of 'Y' or 'N'      |
| NOT       | WHERE Col NOT IN ('Y', 'N') | NOT is frequently used with LIKE and IN               |
| AND       | WHERE Col1 > 5 AND Col2 < 3 | Filter rows where two or more conditions must be true |
| OR        | WHERE Col1 > 5 OR Col2 < 3  | Filter rows where at least one condition must be true |
| BETWEEN   | WHERE Col BETWEEN 3 AND 5   | Often easier syntax than using an AND                 |




### Resources: 
    - https://classroom.udacity.com/courses/ud198
    - Designing Data-Intensive Applications: The Big Ideas Behind Reliable, Scalable, and Maintainable Systems
    - https://www.datasciencecourse.org/notes/relational_data/
----------
