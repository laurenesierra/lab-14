# lab-14

## Author

-Lauren Sierra

## Collaborators

    - Glenn Clark

## Overview of Project

Today you will be seeding a database, then executing a series of commands to normalize your data into two tables: books and authors. You will execute a series of SQL commands, as demonstrated in class and detailed below, to normalize your data and remove duplications.

If the normalization is successful, the user will not be aware that anything has changed.

At the end of this process, your tables should be represented in your database as two tables:

1. A table for authors. This table will be referenced by the books table, below:

```
                                Table "public.authors"
  Column   |          Type          | Collation | Nullable |                Default
-----------+------------------------+-----------+----------+---------------------------------------
 id        | integer                |           | not null | nextval('authors_id_seq'::regclass)
 name      | character varying(255) |           |          |
Indexes:
    "authors_pkey" PRIMARY KEY, btree (id)
Referenced by:
    TABLE "books" CONSTRAINT "fk_author" FOREIGN KEY (author_id) REFERENCES authors(id)

 ```

 1. A table for books. This table will have a author_id property which is a foreign key that references the id property of the authors table:

 ```
        Table "public.books"
    Column    |          Type          | Collation | Nullable |              Default
--------------+------------------------+-----------+----------+-----------------------------------
 id           | integer                |           | not null | nextval('books_id_seq'::regclass)
 title        | character varying(255) |           |          |
 author       | character varying(255) |           |          |
 isbn         | character varying(255) |           |          |
 image_url    | character varying(255) |           |          |
 description  | text                   |           |          |
 author_id    | integer                |           |          |
Indexes:
    "books_pkey" PRIMARY KEY, btree (id)
Foreign-key constraints:
    "fk_author" FOREIGN KEY (author_id) REFERENCES authors(id)

    ```


## Number and name of feature: #1 Normalize Database

Estimate of time needed to complete: 1 hr

Start time: 6:40

Finish time: 8:30

Actual time needed to complete: 1:50