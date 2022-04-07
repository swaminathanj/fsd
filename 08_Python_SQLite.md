# Python with SQLite


## 1. Connecting to database

Demonstrates the connecting to the database test.db. If test.db does not exist, it will be created and connection object (conn) is returned.
 
 ```python
import sqlite3

conn = sqlite3.connect('test.db')
```

## 2. Creating table

After making a connection, you can create a table by wrapping the SQL CREATE TABLE query 

```python
import sqlite3

conn = sqlite3.connect('test.db')

conn.execute('''CREATE TABLE Student (
  Id INT PRIMARY KEY NOT NULL, 
  Name VARCHAR(30) NOT NULL, 
  DoB DATE NOT NULL, 
  Degree VARCHAR(20)); ''')
  
conn.close()
```

## 3. Insert into table

```python
import sqlite3

conn = sqlite3.connect('test.db')

conn.execute( "INSERT INTO Students VALUES (1, "Ashok", '2000-10-27', 'M.Tech')" )

conn.execute( "INSERT INTO Students (Name, Id, Degree, DoB) VALUES ("Binu", 2, 'M.Tech', '2000-07-15')" )

conn.execute( "INSERT INTO Students (Id, Name, Id, Degree, DoB) \
        VALUES (3, "Caesar", 'B.Tech', '2002-02-09')" )

conn.execute( "INSERT INTO Students VALUES \
        (4, "Daniel", '2002-02-09', 'M.C.A')" )
        
conn.commit()

conn.close()
```

## 4. Retrieve from table

```python
import sqlite3

conn = sqlite3.connect('test.db')

cursor = conn.execute("SELECT id, name, address, salary from COMPANY")
for row in cursor:
   print( "Id = ", row[0], " | Name = ", row[1], " | DoB = ", row[2], " | SALARY = ", row[3] )
   # print( row )  # Comment out above and uncomment this, check the output
   
conn.close()
```
