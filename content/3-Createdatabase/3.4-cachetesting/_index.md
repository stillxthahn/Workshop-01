---
title : "Insert data into database"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 3.4. </b> "
---

### Insert data into database
1. First, we have to install the required Python packages

 - **```pip install redis mysql-connector-python faker```**

2. Next, we will create a Python script to query data from RDS and dump it into JSON. We will use the following code (replace host with your RDS Endpoint):

	```from faker import Faker
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

	batch_size = 1000
	todos = []

	for _ in range(1000):
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
 - Using MySQL Workbench, we can see that the data has been inserted into the database.
![ConnectPrivate](/images/3.Createdatabase/3.4-cachetesting/001-cachetesting.png)

 


  

