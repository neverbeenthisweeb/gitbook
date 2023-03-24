# DB and Table

**Contents**

* Create DB
* Create Table

## Create DB

Let's start from an empty directory.

```
➜  sqlite-demo ls
➜  sqlite-demo 
```

We are going to create a DB named `demo.db`.

To create a DB:

```
➜  sqlite-demo sqlite3 demo.db
SQLite version 3.38.4 2022-05-04 15:45:55
Enter ".help" for usage hints.
sqlite> 
```

After you execute `sqlite3 demo.db`, you are ready to interact with sqlite3's CLI.

## Create Table

Here, we will create a `books` table to store information related to book keeping.

To create a table and check for existing tables:

```sql
sqlite> CREATE TABLE books(
   ...> id INT,
   ...> name TEXT,
   ...> author TEXT
   ...> );
sqlite> .tables
books
```
