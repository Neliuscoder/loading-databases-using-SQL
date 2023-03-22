# loading-databases-using-SQL
This repository contains an example of how to load a SQLite database using Python and the SQLite3 library.

Requirements

Python 3

SQLite3
Usage

Create a SQLite database file (.db file extension) or use an existing one.

In your Python script, import the SQLite3 library:


import sqlite3

Establish a connection to the database using the connect() method of the sqlite3 module:



conn = sqlite3.connect('mydatabase.db')

Replace mydatabase.db with the name of your database file.


Create a cursor object using the cursor() method of the connection object:

cur = conn.cursor()

Execute SQL commands using the execute() method of the cursor object:

cur.execute("CREATE TABLE IF NOT EXISTS users (id INTEGER PRIMARY KEY, name TEXT, age INTEGER)")

This example creates a table called users with three columns: id, name, and age.


Insert data into the database using the execute() method:


cur.execute("INSERT INTO users (name, age) VALUES (?, ?)", ("John", 30))


This example inserts a new row into the users table with the name and age values of "John" and 30, respectively.




Commit changes to the database using the commit() method of the connection object:

conn.commit()

Close the connection when you're finished working with the database:


conn.close()

