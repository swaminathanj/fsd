# SQLite Basics

## 1. Create Database
Create a database (test.db) and start the SQLite session.

```
CMD>sqlite3 test.db
SQLite version 3.38.2 2022-03-26 13:51:10
Enter ".help" for usage hints.
sqlite>
sqlite> .databases
main: D:\Swaminathan\Academics\2022 Jan FSD\sqlite\test.db r/w
```

## 2. Create a Table
Create a STUDENT table with
* Roll number - an integer attribute and also the primary key
* Name - a variable lengthed string
* Degree - a variable lengthed string
* DoB - a date variable

```
sqlite> CREATE TABLE [Students] (
   ...> Id INTEGER PRIMARY KEY NOT NULL,
   ...> Name VARCHAR(30) NOT NULL,
   ...> Degree VARCHAR(20),
   ...> DoB DATE
   ...> );
sqlite> .tables
Students
sqlite>
```

You can delete or rename a table by using DROP and ALTER commands. You can try this at leisure. The syntax for both is given below.
* DROP &langle;table_name&rangle; ;
* ALTER &langle;old_name&rangle; RENAME TO &langle;new_name&rangle; ;

Use .tables to check for the changed effect.

NOTE: There are more data types in SQL which you can explore at leisure.

## 3. Insert Values into Table
The following SQL commands demonstrates different INSERT examples.

### a. You can specify the field names and provide the values in that order
```
sqlite> INSERT INTO Students (Id, Name, Degree, DoB) VALUES (1, 'Amit', 'M.Tech', '2000-09-15');
```

### b. You don't need to specify fields if values are in the same order as fields
```
sqlite> INSERT INTO Students VALUES (2, 'Ashok', 'M.Tech', '2000-06-13');
```
### c. Values to optional fields need not be given
```
sqlite> INSERT INTO Students (Id, Name, Degree) VALUES (11, 'Seema', 'B.Tech');
sqlite> INSERT INTO Students (Id, Name, DoB) VALUES (13, 'Kamal', '2002-05-17');
sqlite> INSERT INTO Students (Id, Name) VALUES (12, 'George');
```
### d. Missing value for compulsory fields leads to insertion error
```
sqlite> INSERT INTO Students (Id, Degree, DoB) VALUES (7, 'M.Tech', '2000-09-15');
Runtime error: NOT NULL constraint failed: Students.Name (19)
```

### e. Duplicate primary key values leads to insertion error
```
sqlite> INSERT INTO Students (Id, Name, Degree, DoB) VALUES (1, 'Swapna', 'M.Tech', '2000-03-22');
Runtime error: UNIQUE constraint failed: Students.Id (19)
```

## 4. Retrieve values from Table

You can use SELECT command to retrieve values from the table.

### a. Retrieve values of all fields from table
```
sqlite> SELECT * FROM Students;
1|Amit|M.Tech|2000-09-15
2|Ashok|M.Tech|2000-06-13
11|Seema|B.Tech|
12|George||
13|Kamal||2002-05-17
```

### b. Retrieve values of selected fields from table
```
sqlite> SELECT Name, DoB FROM Students;
Amit|2000-09-15
Ashok|2000-06-13
Seema|
George|
Kamal|2002-05-17
```

## c. Retrieve values based on condition

```
sqlite> SELECT * FROM Students WHERE Id > 5;
11|Seema|B.Tech|
12|George||
13|Kamal||2002-05-17
```

This is the case of no value matching the condition
```
sqlite> SELECT * FROM Students WHERE iD = 5;
sqlite>
```

## d. Retrieve values based on similarity
The LIKE is used in conjuction with _ for single wildcard char or % for any number of wildcard chars.

```
sqlite> SELECT * FROM Students WHERE Degree LIKE '%Tech';
1|Amit|M.Tech|2000-09-15
2|Ashok|M.Tech|2000-06-13
11|Seema|B.Tech|

sqlite> SELECT * FROM Students WHERE Degree like '_.Tech';
1|Amit|M.Tech|2000-09-15
2|Ashok|M.Tech|2000-06-13
11|Seema|B.Tech|

sqlite> SELECT * FROM Students WHERE DoB like '2000%';
1|Amit|M.Tech|2000-09-15
2|Ashok|M.Tech|2000-06-13
```

### e. Retrieving values with multiple conditions

```
sqlite> SELECT * FROM Students WHERE Id > 1 AND Id < 12;
2|Ashok|M.Tech|2000-06-13
11|Seema|B.Tech|

sqlite> SELECT * FROM Students WHERE Id > 1 AND DoB LIKE '2002%';
13|Kamal||2002-05-17
```

## 5. Updating values in table

Before updating lets check the table values first.
```
sqlite> SELECT * FROM Students;
1|Amit|M.Tech|2000-09-15
2|Ashok|M.Tech|2000-06-13
11|Seema|B.Tech|
12|George||
13|Kamal||2002-05-17
```
Let's update the values.
```
sqlite> UPDATE Students SET DoB = '2002-11-23' WHERE Id = 11;
sqlite> UPDATE Students SET Degree = 'MCA', DoB = '2001-04-30' WHERE Id = 12;
sqlite> UPDATE Students SET Degree = 'B.Tech' WHERE Name = 'Kamal';
```
Now check if the values are really updated.
```
sqlite> SELECT * FROM Students;
1|Amit|M.Tech|2000-09-15
2|Ashok|M.Tech|2000-06-13
11|Seema|B.Tech|2002-11-23
12|George|MCA|2001-04-30
13|Kamal|B.Tech|2002-05-17
```

## 6. Delete values from table

First delete.
```
sqlite> DELETE FROM Students WHERE Name like 'K%';
```
Then check.
sqlite> SELECT * FROM Students;
1|Amit|M.Tech|2000-09-15
2|Ashok|M.Tech|2000-06-13
11|Seema|B.Tech|2002-11-23
12|George|MCA|2001-04-30
```
Note:
* If the WHERE condition matches multiple values, all of them will get deleted.
* DELETE FROM Students will remove all the values of Students.
* DROP Students will delete the table itself.

