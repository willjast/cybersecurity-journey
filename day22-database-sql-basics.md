# Day 22 – Database SQL Basics

## TryHackMe Room

Database SQL Basics

---

## Room Summary

Today I started and completed the TryHackMe room **Database SQL Basics**.

This room introduced the basics of databases and SQL using a café example. I learned how computers store information in databases, how tables organize data into rows and columns, and how SQL is used to ask questions about stored information.

---

## Topics Covered

### What Is Data?

Data is information that can be stored, processed, searched, and managed by a computer.

Examples of data:

* drink names
* prices
* order times
* customer records
* usernames
* login attempts
* IP addresses
* system logs

In cybersecurity, data is important because logs, alerts, user accounts, and system activity are often stored in databases or table-like structures.

---

### What Is a Database?

A database is an organized place where a computer stores information.

A database makes it easier to:

* store large amounts of information
* search information quickly
* sort records
* filter records
* manage data more efficiently than using paper notes or simple files

In the café example, a database helps the owner track orders, prices, and times without manually searching through a paper notebook.

---

### Tables, Rows, and Columns

A database stores information inside tables.

A table is similar to a spreadsheet.

Example café table:

| id | drink  | price | time  |
| -- | ------ | ----- | ----- |
| 1  | Coffee | 2.50  | 09:00 |
| 2  | Tea    | 2.00  | 09:05 |
| 3  | Latte  | 4.50  | 09:10 |

---

## Key Database Terms

### Table

A table stores related information in rows and columns.

Example:

```text
Orders
```

The `Orders` table stores café orders.

---

### Column

A column stores one type of information.

Examples:

```text
id
drink
price
time
```

Each column represents a category of data.

---

### Row

A row stores one complete record.

In the café example:

```text
One row = one complete café order
```

If the café sells 10 drinks, the table has 10 rows.

If one more customer places an order, one more row is added.

---

### Record

A record is one complete set of information in a table.

Example:

| id | drink | price | time  |
| -- | ----- | ----- | ----- |
| 2  | Tea   | 2.00  | 09:05 |

This row is one full record.

---

## What Is SQL?

SQL stands for:

```text
Structured Query Language
```

SQL is a language used to communicate with databases.

SQL can be used to:

* retrieve information
* filter information
* sort information
* add data
* update data
* delete data

In this room, I mainly practised retrieving, filtering, and sorting information.

---

## SQL Keywords Learned

### SELECT

`SELECT` chooses what data to display.

Example:

```sql
SELECT drink FROM Orders;
```

Meaning:

```text
Show the drink column from the Orders table.
```

---

### FROM

`FROM` chooses which table the data comes from.

Example:

```sql
SELECT * FROM Orders;
```

Meaning:

```text
Show everything from the Orders table.
```

---

### WHERE

`WHERE` filters rows based on a condition.

Example:

```sql
SELECT * FROM Orders WHERE drink = 'Coffee';
```

Meaning:

```text
Show only the rows where the drink is Coffee.
```

---

### ORDER BY

`ORDER BY` sorts the results.

Example:

```sql
SELECT * FROM Orders ORDER BY price;
```

Meaning:

```text
Show all orders and sort them by price from lowest to highest.
```

---

### DESC

`DESC` sorts results in descending order.

Example:

```sql
SELECT * FROM Orders ORDER BY price DESC;
```

Meaning:

```text
Show all orders and sort them by price from highest to lowest.
```

---

## SQL Queries Practised

### Show Everything From a Table

```sql
SELECT * FROM Orders;
```

The `*` symbol means all columns.

This query displays every row and every column from the `Orders` table.

---

### Show Only Specific Columns

```sql
SELECT drink, price FROM Orders;
```

This query displays only the `drink` and `price` columns.

---

### Filter Results

```sql
SELECT * FROM Orders WHERE drink = 'Coffee';
```

This query displays only orders where the drink is Coffee.

Important note:

Text values usually need quotation marks.

Correct:

```sql
WHERE drink = 'Coffee';
```

Incorrect:

```sql
WHERE drink = Coffee;
```

Without quotes, the database may treat `Coffee` as a column name instead of text.

---

### View the Menu Table

```sql
SELECT * FROM Menu;
```

This query shows all available drinks and prices in the `Menu` table.

This is useful when I need to check the exact drink names available in the database.

---

### Sort Results From Lowest to Highest

```sql
SELECT * FROM Orders ORDER BY price;
```

This sorts orders by price in ascending order.

Ascending means:

```text
lowest to highest
A to Z
oldest to newest
```

---

### Sort Results From Highest to Lowest

```sql
SELECT * FROM Orders ORDER BY price DESC;
```

This sorts orders by price in descending order.

Descending means:

```text
highest to lowest
Z to A
newest to oldest
```

---

### Combine Filtering and Sorting

```sql
SELECT * FROM Orders WHERE drink = 'Coffee' ORDER BY price DESC;
```

This query does two things:

1. Shows only Coffee orders
2. Sorts those Coffee orders from highest price to lowest price

---

## Basic SQL Structure

The basic SQL structure I learned is:

```sql
SELECT columns
FROM table
WHERE condition
ORDER BY column;
```

In plain English:

```text
Show me this information
from this table
but only these matching rows
and sort them this way.
```

---

## Important Notes

A `SELECT` query does not change the database. It only reads and displays information.

However, SQL can also be used to change data with other commands, such as:

| SQL Command | Purpose               |
| ----------- | --------------------- |
| SELECT      | Reads/displays data   |
| INSERT      | Adds new data         |
| UPDATE      | Changes existing data |
| DELETE      | Removes data          |

This room focused mainly on `SELECT`.

---

## Security Connection

This room also connects to cybersecurity.

If someone could change or remove café orders without permission, the café could have serious problems.

Possible issues:

* orders could be deleted
* prices could be changed
* fake orders could be added
* reports could become incorrect
* the café could lose money
* the owner could no longer trust the data

This connects to the **Integrity** part of the CIA Triad.

```text
Integrity = making sure data is accurate and not changed without permission
```

In cybersecurity, databases may store:

* usernames
* password hashes
* login attempts
* IP addresses
* security alerts
* firewall logs
* payment records
* system activity

Protecting database integrity is extremely important.

---

## Cybersecurity Example

A login table could look like this:

| id | username | ip_address   | status  | time  |
| -- | -------- | ------------ | ------- | ----- |
| 1  | will     | 192.168.1.10 | success | 08:00 |
| 2  | admin    | 10.0.0.5     | failed  | 08:05 |
| 3  | guest    | 10.0.0.9     | failed  | 08:10 |

A security analyst could use SQL to find failed login attempts:

```sql
SELECT * FROM Logins WHERE status = 'failed';
```

Or show failed logins with the newest first:

```sql
SELECT username, ip_address, time
FROM Logins
WHERE status = 'failed'
ORDER BY time DESC;
```

This shows how SQL can be useful for SOC analysts and cybersecurity investigations.

---

## Cheat Sheet

### Database Basics

```text
Data = information

Database = organized storage for data

Table = data arranged in rows and columns

Column = one type/category of information

Row = one complete record

Record = one full item in a table

SQL = language used to communicate with databases

Query = a request sent to a database
```

---

### SQL Basics

```sql
SELECT * FROM Orders;
```

Show everything from the `Orders` table.

```sql
SELECT drink, price FROM Orders;
```

Show only the `drink` and `price` columns.

```sql
SELECT * FROM Orders WHERE drink = 'Coffee';
```

Show only Coffee orders.

```sql
SELECT * FROM Orders ORDER BY price;
```

Sort orders by price from lowest to highest.

```sql
SELECT * FROM Orders ORDER BY price DESC;
```

Sort orders by price from highest to lowest.

```sql
SELECT * FROM Orders WHERE drink = 'Coffee' ORDER BY price DESC;
```

Show Coffee orders sorted from highest price to lowest price.

---

## Personal Takeaway

Today I learned that databases organize information in tables, and SQL is used to ask clear questions about that information.

The most important idea I learned is:

```text
SELECT = what do I want to see?
FROM = where does the data come from?
WHERE = what condition should the data match?
ORDER BY = how should the results be sorted?
```

This was a beginner-friendly introduction to SQL, but it is also important for cybersecurity because databases store logs, user activity, account information, alerts, and other evidence.

Understanding SQL will help me later with SOC analysis, web application security, and SQL injection.
