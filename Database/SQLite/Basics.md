```sqlite
CREATE TABLE TableName {
	(colName dataType [NOT NULL] [UNIQUE] [DEFAULT defaultOption] [CHECK searchCondition] [...])
	[PRIMARY KEY (listOfColumns)]
	{[FOREIGN KEY (listOfFKColumns) REFERENCES ParentTableName [(listOfCKColumns)], [ON UPDATE referentialAction] [ON DELETE referentialAction]] [...]}
	{[CHECK (searchCondition)] [...]}
}
```

## Datatypes


## Tables
#### Create
```sqlite
CREATE TABLE [IF NOT EXISTS] Staff(
	staffID TEXT PRIMARY KEY,
	fName TEXT NOT NULL,
	lName TEXT NOT NULL,
	salary REAL
);
```

#### Alter
```sqlite
ALTER TABLE Staff Alter position DROP DEFAULT;

ALTER TABLE Client ADD prefNoRooms SMALLINT;

DROP TABLE PropertyForRent;

ALTER TABLE TableName ADD email TEXT;
```

#### View
```sqlite
.schema TableName

.tables
```

## Retrieving Data
#### From multiple tables
For this we use something called **subqueries**
```sqlite
SELECT staffNo, fName, lName
FROM Staff
WHERE branchNo = (
	SELECT branchNo
	FROM Branch
	WHERE street = '164 Main St');

SELECT StaffNo, fName, lName, salary - (SELECT AVG(salary) FROM Staff) As SalDiff
FROM Staff
WHERE salary > (
	SELECT Avg(salary)
	FROM Staff);
```
You can also nest these (like nested for loops) so you can have a `SELECT` inside a `SELECT` inside a `SELECT` etc.

#### Viewing data from multiple tables
```sqlite
SELECT c.clientNo, fName, lName, propertyNo, comment
FROM Client c, Viewing v
WHERE c.clientNo = v.clientNo
```

**Join**
```sqlite
SELECT c.clientNo, fName, lName, propertyNo, comment
FROM Client c JOIN Viewing v 
ON c.clientNo = v.clientNo

SELECT clientNo, fName, lName, propertyNo, comment
FROM Client 
JOIN Viewing USING (clientNo);
```
Using `LEFT/RIGHT JOIN` will take everything from one table and match it to the other table where it can, but if there is no match, it will still show the data but the columns from the other table will show as `NULL`.
`FULL OUTER JOIN` will show all rows that do not match from both tables.

#### Viewing data
```sqlite
.mode column
.headers on
```
This will make the output of your queries look much nicer.

## Checks
#### ANY and ALL
**Only work on subqueries that produce a single column of output**
`ANY` - true if satisfied by AT LEAST ONE value produced by query
`ALL` - True if satisfied by ALL values produced by query
`ALL` can be replaced by `MAX`
`ANY` can be replaced by `MIN`

#### EXISTS and NOT EXISTS
```sqlite
SELECT columns
FROM table
where EXISTS (subquery);
```

#### Set operators
**UNION**
```sqlite
SELECT city
FROM Branch
WHERE city IS NOT NULL 
UNION
SELECT city
FROM PropertyForRent
WHERE city IS NOT NULL;
```

**INTERSECT**
```sqlite
SELECT city FROM Branch
INTERSECT
SELECT city FROM PropertyForRent;
```

**EXCEPT**
```sqlite
SELECT city FROM Branch
EXCEPT
SELECT city FROM PropertyForRent;
```

## Triggers
What happens when certain data is updated.