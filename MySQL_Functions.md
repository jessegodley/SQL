**NEW TABLE: BOOKS**

The BOOKS table is described as follows: (This table will be used for all problems until a new table is declared)

|  Field | Type | NULL | Key | Default | Extra |
|---|---|---|---|---|---|
| book_id | INT | NO | PRI | NULL | auto_increment |
| title | VARCHAR(100)| YES | | NULL | |
| author_fname | VARCHAR(100) | YES | | NULL | |
| author_lname | VARCHAR(100) | YES | | NULL | |
| released_year | INT | YES | | NULL | |
| stock_quantity | INT | YES | | NULL | |
| pages | INT | YES | | NULL | |

**CONCAT and CONCAT_WS FUNCTION**

Create a list of authors full names where first and last name are separated by a space:

**Solution**
```sql
SELECT
  CONCAT(author_fname, ' ', author_lname) AS 'full name'
FROM books;
```
ALSO (to divide each part up and then combine)

```sql
SELECT author_fname AS first, author_lname AS last,
  CONCAT(author_fname, ' ', author_lname) AS full
FROM books;
```

Create a list of book titles and authors full names where first and last name are space hyphenated:

**Solution**
```sql
SELECT
  CONCAT_WS(' - ', title, author_fname, author_lname) AS 'book titles and author'
FROM books;
```
