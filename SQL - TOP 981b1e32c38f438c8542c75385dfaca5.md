# SQL - TOP

## **[Relational Database Management Systems](https://launchschool.com/books/sql/read/introduction#rdbms)**

Now suppose other people in the company are interested in reading the reviews and adding users. Therefore, you decide to share the spreadsheet. Over time, the amount of information starts to increase. You begin to encounter issues with duplicate data, typos, perhaps even formatting issues if multiple people are working on one file. The simple spreadsheet now becomes unwieldy and finding/collecting information requires a lot of scrolling and searching. At this point, you would probably benefit from moving to a **relational database management system**.

A **relational database** is a database organized according to the *relational model* of data. In simple terms, the relational model defines a set of relations (which we can think of as analogous to tables) and describes the relationships, or connections, between them in order to determine how the data stored in them can interact. Using the relational model elevates our database from data that is represented in just a flat, two-dimensional table, to one where we can describe the data in a more complex and detailed way. Using a relational database helps us to cut down on duplicated data and provides a much more useful data structure for us to interact with.

- This is basically like PostGresSQL / SQLite that acts as your relational database management system.
- It is worth noting that the relational model is not the only structured data model used by database software. A program like MongoDB, for example, uses a document-oriented data storage model.

## **[Why learn SQL?](https://launchschool.com/books/sql/read/introduction#whylearnsql)**

Relational databases have become so widespread that you're likely using multiple databases per day without even knowing it. Smaller examples include Firefox, which uses [SQLite](http://www.sqlite.org/) to keep track of the user's history and data, to banking systems which might be using an [Oracle](http://www.oracle.com/index.html) database to store daily transactions.

Another way you may have been using SQL is through a programming language, like Python or Ruby. If you've ever done a tutorial with Ruby on Rails, for example, it's likely the code you wrote generated SQL behind the scenes for you. No matter which language you're using, the database and its data will most likely out-live most of the application code in your program.

Creating a well-designed database is like laying the foundations of a house, and learning SQL and relational database concepts will help you build your applications on a strong foundation. Since databases are such a key part of almost all web applications, understanding the language of databases and how they work is a vital step towards becoming a well-rounded web-developer.

## If we didn't use a Relational Database

![SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled.png](SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled.png)

- You can have endless errors if you don't have a database as the user can input too many things.

![SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%201.png](SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%201.png)

![SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%202.png](SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%202.png)

- You can then put them all into a file and then relate the data to each other using a key name id. We use a primary key that is unique so that the row is unique and then we can reference to them from another database.

![SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%203.png](SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%203.png)

![SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%204.png](SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%204.png)

- Then we can tie things together and so we can now interrelate things together and they are known as foreign keys.

![SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%205.png](SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%205.png)

- That way with the revised form you can add menus for publishers so it forces the user to input their answer correctly.

![SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%206.png](SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%206.png)

- The source for it then looks like this, the integer is actually the primary key for each platform.

![SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%207.png](SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%207.png)

- Don't do this basically

![SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%208.png](SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%208.png)

```jsx
/** Grocery list: 
Bananas (4)
Peanut Butter (1)
Dark Chocolate Bars (2)
**/

CREATE TABLE groceries (id INTEGER PRIMARY KEY, name TEXT, quantity INTEGER );

INSERT INTO groceries VALUES (1, "Bananas", 4);
INSERT INTO groceries VALUES (2, "Peanut Butter", 1);
INSERT INTO groceries VALUES (3, "Dark chocolate bars", 2);
SELECT * FROM groceries;
```

- You can use SELECT to then order things but we can then ORDER BY to then order things.

```jsx
SELECT * FROM groceries ORDER BY aisle;
```

- But then you can also order it with a where clause to filter it out even further than that.

```jsx
SELECT * FROM groceries WHERE aisle > 5 ORDER BY aisle;
```

## To Aggregate Data

```jsx
SELECT SUM(quantity) FROM groceries;
```

- You say what you want to select, the thing you want to sum and from where.

![SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%209.png](SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%209.png)

- If you then want to see which is the MAX amount in your quantity you just use the keyword MAX.

```jsx
SELECT MAX(quantity) FROM groceries;
```

- If you want to see it grouped by aisle in this case we just use SELECT and add which aisle we want and

```jsx
SELECT aisle, SUM(quantity) FROM groceries GROUP BY aisle;
```

- With select by name it basically groups by the first thing it see's and not alphabetically so thats not the best.

## Databases and SQL

SQL queries is pretty important. I actually think of Excel tables moving in my head and combining with each other and reshuffling as necessary. To each their own.

All this stuff is being used by Rails behind the scenes so understanding it will make you much better at writing queries in Rails. This is why we’re going over databases before learning Rails.

### **Statements:**

- `SELECT`
- `CREATE TABLE`
- `DROP TABLE`
- `CREATE INDEX`
- `DROP INDEX`
- `UPDATE`
- `DELETE`
- `INSERT INTO`
- `CREATE DATABASE`
- `DROP DATABASE`
- `COMMIT` (concept)
- `ROLLBACK` (concept)

### **Clauses:**

- `DISTINCT`
- `WHERE`
- `IN`
- `AND`
- `OR`
- `BETWEEN`
- `LIKE`
- `ORDER BY`
- `COUNT`

### **Functions**

- `GROUP BY`
- `HAVING`
- `AVG`
- `COUNT`
- `MIN`
- `MAX`
- `SUM`

SQL is the language used to talk to many relational databases. These databases use lots of tables to store different types of data (e.g. “users” and “posts” tables). Tables are long lists like spreadsheets where each row is a different record (or object, e.g. a single user) and each column is one of that record’s attributes (like name, email, etc). The one column that all tables include is an “ID” column, which gives the unique row numbers, and is called the record’s “primary key”.

You can “link” tables together by making one of the columns in one table point to the ID of another table, for instance a row in the “posts” table might include the author’s ID under the column called “user_id”. Because the “posts” table has the ID of another table in it, that column is called a “foreign key”.

SQL lets you do everything. The first category of commands are for setting up the database (`CREATE DATABASE`), setting up an individual table (`CREATE TABLE`), and similar commands for altering or destroying them. The setup information for your database is stored in a special file called the “Schema”, and this is updated whenever you make changes to the structure of your database. Think of the schema as saying “here’s our database and it’s got a couple tables. The first table is ‘users’ and it’s got columns for ‘ID’ (which is an integer), ‘name’ (which is a bunch of characters), ‘email’ (which is a bunch of characters) …”

In addition to setting up tables, you can tell your database to only allow unique values in a particular column (e.g. for usernames) or to index a column for faster searching later with `CREATE INDEX`. Create indexes, which basically do all the hard work of sorting your table ahead of time, for columns that you’ll likely be using to search on later (like username)… it will make your database much faster.

SQL likes semicolons at the end of lines and using single quotes (‘) instead of double quotes(“).

## CRUD in sql

Every CRUDdy command in SQL contains a few parts – the action (“statement”), the table it should run on, and the conditions (“clauses”). If you just do an action on a table without specifying conditions, it will apply to the whole database and you’ll probably break something.

For “Destroy” queries, the classic mistake is typing DELETE * FROM users without a WHERE clause, which removes all your users from the table. You probably needed to delete just one user, who you would specify based on some (hopefully unique) attribute like “name” or “id” as part of your condition clause, e.g. DELETE * FROM users WHERE [users.id](http://users.id/) = 1. You can do all kinds of common sense things like using >, <, <= etc. comparison operators to specify groups of rows to run commands on or logical operators like AND, OR, NOT etc to chain multiple clauses together, e.g. DELETE * FROM users WHERE id > 12 AND name = 'foo'.

“Create” queries use `INSERT INTO` and you’ll need to specify which columns to insert stuff into and then which values to put in those columns, which looks something like `INSERT INTO Users (name, email) VALUES ('foobar','foo@bar.com');`. This is one of the few queries that you don’t need to be careful about which rows you’ve selected since you’re actually just adding new ones into the table.

“Update” queries use `UPDATE` and you’ll need to tell it what data to `SET` (using key=”value” pairs) and which rows to do those updates for. Be careful because if your `WHERE` clause finds multiple rows (e.g. if you’ve searched based on a common first name), they’ll all get updated. A standard query for updating a user’s email may look something like the following (though in the real world you’d search on ID because it’s always unique):

```jsx
  UPDATE Users
  SET name='barfoo', email='bar@foo.com'
  WHERE email='foo@bar.com';
```

“Read” queries, which use `SELECT`, are the most common, e.g. `SELECT * FROM users WHERE created_at < '2013-12-11 15:35:59 -0800'`. The `*` you see just says “all the columns”. Specify a column using both the table name and the column name. You can get away with just the column name for simple queries but as soon as there are more than one table involved, SQL will yell at you so just always specify the table name: `SELECT users.id, users.name FROM users`.

A close cousin of `SELECT`, for if you only want unique values of a column, is `SELECT DISTINCT`. Say you want a list of all the different names of your users without any duplicates… try `SELECT DISTINCT users.name FROM users`.

### Visual explanation of SQL JOIN

[https://blog.codinghorror.com/a-visual-explanation-of-sql-joins/](https://blog.codinghorror.com/a-visual-explanation-of-sql-joins/)

![SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%2010.png](SQL%20-%20TOP%20981b1e32c38f438c8542c75385dfaca5/Untitled%2010.png)

### Join Instructions

1. `INNER JOIN`, aka `JOIN` – Your best friend and 95% of what you’ll use. Keeps only the rows from both tables where they match up. If you asked for all the posts for all users (`SELECT * FROM users JOIN posts ON users.id = posts.user_id`), it would return only the users who have actually written posts and only posts which have specified their author in the `user_id` column. If an author has written multiple posts, there will be multiple rows returned (but the columns containing the user data will just be repeated).
2. `LEFT OUTER JOIN` – keep all the rows from the left table and add on any rows from the right table which match up to the left table’s. Set any empty cells this produces to `NULL`. E.g. return all the users whether they have written posts or not. If they do have posts, list those posts as above. If not, set the columns we asked for from the “posts” table to `NULL`.
3. `RIGHT OUTER JOIN` – the opposite… keep all rows in the right table.
4. `FULL OUTER JOIN` – Keep all rows from all tables, even if there are mismatches between them. Set any mismatched cells to `NULL`.

Joins naturally let you specify conditions too, like if you only want the posts from a specific user: `SELECT * FROM users JOIN posts ON users.id = posts.user_id WHERE users.id = 42`.

### **Using Functions to Aggregate Your Data**

When you run a vanilla SQL query, you often get back a bunch of rows. Sometimes you want to just return a single relevant value that aggregates a column, like the `COUNT` of posts a user has written. In this case, just use one of the helpful “aggregate” functions offered by SQL (most of which you’d expect to be there – functions like `SUM` and `MIN` and `MAX` etc). You include the function as a part of the `SELECT` statement, like `SELECT MAX(users.age) FROM users`. The function will operate on just a single column unless you specify `*`, which only works for some functions like `COUNT` (because how would you `MAX` a column for “name”?).

You often see aliases (`AS`) used to rename columns or aggregate functions so you can call them by that alias later, e.g. `SELECT MAX(users.age) AS highest_age FROM users` will return a column called `highest_age` with the maximum age in it.

Now we’re getting into the fun stuff. Aggregate functions like `COUNT` which return just a single value for your whole dataset are nice, but they become really useful when you want to use them on very specific chunks of your data and then group them together, e.g. displaying the `COUNT` of posts for EACH user (as opposed to the count of all posts by all users). That would look like:

```jsx
  SELECT users.id, users.name, COUNT(posts.*) AS posts_written
  FROM users
  JOIN posts ON users.id = posts.user_id
  GROUP BY users.id;
```

- Suddenly you can show data that interesting like how many posts someone has done.

### **[SQL is faster than Ruby!](https://www.theodinproject.com/paths/full-stack-ruby-on-rails/courses/databases/lessons/databases-and-sql#sql-is-faster-than-ruby)**

Learning this stuff is particularly relevant because it’s MUCH faster for you to build queries that use SQL intelligently than to just grab a whole bunch of data out of your database and then use Ruby to process it. For instance, if you want all the unique names of your users, you COULD just grab the whole list from your database using SQL like `SELECT users.name FROM users` (which Active Record will do for you with `User.select(:name)`) then remove duplicates using Ruby’s `#uniq` method, e.g. `User.select(:name).uniq`… but that requires you to pull all that data out of your database and then put it into memory and then iterate through it using Ruby. Use `SELECT DISTINCT users.name FROM users` instead to have SQL do it all in one step.

SQL is built to be fast. It has a special query optimizer which takes a look at the whole query you’re about to run and it figures out exactly which tables it needs to join together and how it can most quickly execute the query. The difference between using `SELECT` and `SELECT DISTINCT` is negligible compared to the time cost of doing it in Ruby. Learning your SQL will help you write Active Record queries that can do more which will make your app much faster.