# SQL

## DDL statements

Data Definition Language statements `CREATE`, `ALTER`, and `DROP` allow us to manage database objects like tables and columns.

### CREATE

```
CREATE TABLE teams
( 
  id           INTEGER      NOT NULL  PRIMARY KEY,
  name         VARCHAR(37)  NOT NULL,
  conference   VARCHAR(2)   NULL
)
```

### ALTER

```
ALTER TABLE teams DROP COLUMN conference
```

### DROP

```
DROP TABLE teams
```

## DML statements

Managing our data may be accomplished in several ways: adding data to the table, updating some of the data, inserting some more data, or deleting some or all of it.

### INSERT

Each set of values creates a new row.

DB2, PostgreSQL, and MySQL allow multiple row constructors.

```
INSERT INTO teams
  ( id , name , conference )
VALUES
  (  9 , 'Riff Raff' , 'F' ) ,
  ( 37 , 'Havoc'     , 'F' ) ,
  ( 63 , 'Brewers'   , 'C' )
```

SQL Server does not allow multiple row constructors.

```
INSERT INTO teams
  ( id , name , conference )
VALUES
  ( 9 , 'Riff Raff' , 'F' )
;

INSERT INTO teams
  ( id , name , conference )
VALUES
  ( 37 , 'Havoc' , 'F' )
;

INSERT INTO teams
  ( id , name , conference )
VALUES
  ( 63 , 'Brewers' , 'C' )
;
```

### UPDATE

Changes the data contained within a table.

#### UPDATE one row

```
UPDATE
  teams
SET
  conference = 'E' 
WHERE
  id = 9
```

#### UPDATE multiple rows

```
UPDATE
  personnel
SET
  salary = salary * 1.07
WHERE
  jobgrade <= 4
```

#### UPDATE every row

```
UPDATE
  personnel
SET
  salary = salary * 1.07
```

### DELETE

Removes entire rows of data from a table.

```
DELETE
FROM
  teams
WHERE
  id = 63
```

### SELECT

#### Syntax

```
SELECT expression(s) involving keywords, identifiers, and constants
FROM tabular structure(s)
```

#### 'SELECT' 1 column

```
SELECT
  name
FROM
  teams
```

#### 'SELECT' multiple columns

```
SELECT
  id, name, conference
FROM
  teams
```

#### 'SELECT' every column

```
SELECT
  *
FROM
  teams
```