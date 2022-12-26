# getting started with sqlite

```
$ sudo apt install sqlite3
```

There are many databases out there. We'll focus on the simplest one first called
`sqlite`. For our projects we use PostgreSQL, but as an introduction to SQL sqlite
is a good start.

To create a database for our `bookHunt` app,

```
sqlite3 book_hunt.db
```

Now we'd be inside sqlite and not our shell.


```
sqlite>

CREATE TABLE novels
(
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  name TEXT,
  createdAt TEXT,
  updatedAt TEXT
);

```

this is an example of DDL - data definition language

to view tables
```
.tables
```

to see the schema of a table

```
.schema tablename
```

## Create

inserting an entry

```
INSERT INTO novels
(name, createdAt, updatedAt)
VALUES
("Harry Potter", "2022-12-26T06:37:45.977Z", "2022-12-26T06:37:45.977Z");

INSERT INTO novels
(name, createdAt, updatedAt)
VALUES
("IT", "2022-12-26T06:39:08.243Z", "2022-12-26T06:39:08.243Z"),
("Alice in wonderland", "2022-12-26T06:39:33.481Z", "2022-12-26T06:39:33.481Z");

```

## Read

```
sqlite> select id, name from novels;
sqlite> select * from novels;
1|Harry Potter|2022-12-26T06:37:45.977Z|2022-12-26T06:37:45.977Z
2|IT|2022-12-26T06:39:08.243Z|2022-12-26T06:39:08.243Z
3|Alice in wonderland|2022-12-26T06:39:33.481Z|2022-12-26T06:39:33.481Z
sqlite> select * from novels where id < 2;
1|Harry Potter|2022-12-26T06:37:45.977Z|2022-12-26T06:37:45.977Z
sqlite> select * from novels where id =2;
2|IT|2022-12-26T06:39:08.243Z|2022-12-26T06:39:08.243Z
```

## Update

```
sqlite> update novels set name="Harry Potter 2" where id =1;
```

## Delete

```
sqlite> delete from novels where id =1;
sqlite> select * from novels;
2|IT|2022-12-26T06:39:08.243Z|2022-12-26T06:39:08.243Z
3|Alice in wonderland|2022-12-26T06:39:33.481Z|2022-12-26T06:39:33.481Z
```

## resources

- https://www.youtube.com/watch?v=p3qvj9hO_Bo
- https://falksangdata.no/wp-content/uploads/2021/04/Opensource.com_cheat_sheet_sqlite_3.pdf
- https://dbeaver.io/
