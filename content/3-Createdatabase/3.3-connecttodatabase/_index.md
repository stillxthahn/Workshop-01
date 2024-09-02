---
title : "Connect to database"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.3. </b> "
---

### Connect to database
In this section, we will initialize our RDS with MySQL workbench
1. First, we will connect with RDS and create our database schema with following script
``` 
CREATE DATABASE todolist; 
USE todolist;
CREATE TABLE todos ( id INT AUTO_INCREMENT, task VARCHAR(255), progress VARCHAR(255), note VARCHAR(255), PRIMARY KEY (id) ); 
```
![ConnectPrivate](/images/3-Createdatabase/3.2-createdbinstances/020-createdbinstances.png)

2. Next, we will use some basic Python code to insert 100 rows of data
 - Install the required Python packages: **```pip install redis mysql-connector-python faker```**
 - Execute the following Python script to insert 100 rows of data. Replat **YOUR_RDS_ENDPOINT** with your RDS Endpoint

	```
	from faker import Faker
	import mysql.connector
	import time
	import random

	fake = Faker()

	# Connect to your MySQL database
	connection = mysql.connector.connect(
		host=YOUR_RDS_ENDPOINT,
		user="admin",
		password="12345678",
		database="todolist"
	)

	connection.autocommit = False
	cursor = connection.cursor()

	start_time = time.time()

	batch_size = 10
	todos = []

	for _ in range(100):
		task = fake.sentence(nb_words=6)
		progress = random.choice(["ON GOING", "DONE"])
		note = fake.sentence(nb_words=10)
		todos.append((task, progress, note))
		
		if len(todos) >= batch_size:
			cursor.executemany("INSERT INTO todos (task, progress, note) VALUES (%s, %s, %s)", todos)
			todos = []  

	if todos:
		cursor.executemany("INSERT INTO todos (task, progress, note) VALUES (%s, %s, %s)", todos)

	connection.commit()

	cursor.close()
	connection.close()
	```

3. Using MySQL Workbench, we can see that the data has been inserted into the database.
![ConnectPrivate](/images/3-Createdatabase/3.3-connecttodatabase/001-connecttodatabase.png)

  

