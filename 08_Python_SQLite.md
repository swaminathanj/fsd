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
```
