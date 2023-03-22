# CRUD

**Contents**

* Create
* Read
* Update
* Delete

## Create

To create data:

```sql
sqlite> INSERT INTO books (id, name, author)
   ...> VALUES
   ...> (1, 'mybook', 'myauthor');
```

## Read

To read data:

```sql
sqlite> SELECT * FROM books;
1|mybook|myauthor
```

## Update

Before simulating an update, let's first add one data to the `books` table.

```sql
sqlite> INSERT INTO books (id, name, author)
   ...> VALUES
   ...> (1, 'herbook', 'herauthor');
```

```sql
sqlite> SELECT * FROM books;
1|mybook|myauthor
2|hername|herauthor
```

To update data with `id` of `1`:

```sql
sqlite> UPDATE books
   ...> SET author = 'newauthor'
   ...> WHERE id = 1;
```

```sql
sqlite> SELECT * FROM books;
1|mybook|newauthor
2|hername|herauthor
```

## Delete

To delete data with `id` of `1`:

```sql
sqlite> DELETE FROM books
   ...> WHERE id = 1;
```

```sql
sqlite> SELECT * FROM books;
2|hername|herauthor
```
