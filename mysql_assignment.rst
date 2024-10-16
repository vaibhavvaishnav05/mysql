Q1. What is a database? Differentiate between SQL and NoSQL databases.
ans.databse is a collection of data where we store instructions and many files.
the main difference between sql and nosql is sql is a relational database but no sql is not a relational database.
sql is a structured query language and nosql is dynamic query language


Q2. What is DDL? Explain why CREATE, DROP, ALTER, and TRUNCATE are used with an example.
ans.ddl is a data control language in sql.
create is use to create format in sql like table database.
drop is use to remove the table from database.
alter is  use to structure of the database.
truncate is use to remove data from tables.



.. code:: ipython3

    %pip install jupysql --quiet


.. parsed-literal::

    Note: you may need to restart the kernel to use updated packages.
    

%%sql sqlite://
CREATE TABLE
  languages (name, rating, change);

INSERT INTO
  languages
VALUES
  ('Python', 14.44, 2.48);

INSERT INTO
  languages
VALUES
  ('C', 13.13, 1.50);

INSERT INTO
  languages
VALUES
  ('Java', 11.59, 0.40);

INSERT INTO
  languages
VALUES
  ('C++', 10.00, 1.98);

Q3. What is DML? Explain INSERT, UPDATE, and DELETE with an example.
ans.DML is a database manipulation language.the sql command which deals with manipulation of data present in database.
insert is use to add data in the table columns.
update is use in sql repalce the data in the sql.
delete is use to remove the data


Q4. What is DQL? Explain SELECT with an example.
ans.DQL is a data query language used to retrive data


Q5. Explain Primary Key and Foreign Key.

               primary key                      foreign key
Uniqueness	Must be unique in the table.	Can contain duplicate values.
NULL Values	Cannot be NULL.	                Can have NULL values.
Purpose	Uniquely identifies a record.	    Links two tables and enforces referential integrity.
Table	Defined in the same table.	    References a primary key in another table.

Q6. Write a python code to connect MySQL to python. Explain the cursor() and execute() method.



import mysql.connector

# Establish a connection to the MySQL database
connection = mysql.connector.connect(
    host="localhost",       # Replace with your database host (e.g., 'localhost')
    user="your_username",    # Replace with your MySQL username
    password="your_password",# Replace with your MySQL password
    database="your_database" # Replace with the database name you want to connect to
)

# Create a cursor object to interact with the database
cursor = connection.cursor()

# Execute a SQL query using the cursor
cursor.execute("SELECT * FROM Employees")

# Fetch all



Q7. Give the order of execution of SQL clauses in an SQL query.
Order of Execution of SQL Clauses:
FROM
JOIN
WHERE
GROUP BY
HAVING
SELECT
DISTINCT
ORDER BY
LIMIT / OFFSET
Detailed Explanation:
FROM:
The FROM clause is executed first. It specifies the table(s) from which the data is retrieved.

Example:
sql
Copy code
SELECT * FROM Employees;
The query starts by fetching the data from the Employees table.

JOIN:
If there are any joins (like INNER JOIN, LEFT JOIN, etc.), they are processed next. The query combines data from multiple tables based on the join condition.

Example:
sql
Copy code
SELECT * FROM Employees INNER JOIN Departments ON Employees.DeptID = Departments.DeptID;
Here, the JOIN clause combines rows from the Employees and Departments tables based on the matching DeptID.

WHERE:
The WHERE clause filters rows based on the condition provided. Only the rows that satisfy the condition are passed to the next stage.

Example:
sql
Copy code
SELECT * FROM Employees WHERE Salary > 5000;
After fetching the data, the query filters out rows where the salary is not greater than 5000.

GROUP BY:
The GROUP BY clause groups the result set by one or more columns. It is usually used when aggregate functions (like SUM(), COUNT(), etc.) are involved.

Example:
sql
Copy code
SELECT Department, COUNT(*) FROM Employees GROUP BY Department;
The query groups the employees by department and counts the number of employees in each department.

HAVING:
The HAVING clause filters the grouped data. It is similar to the WHERE clause but is applied after the GROUP BY and works on aggregated data.

Example:
sql
Copy code
SELECT Department, COUNT(*) FROM Employees GROUP BY Department HAVING COUNT(*) > 5;
The query filters the groups where the number of employees is greater than 5.

SELECT:
The SELECT clause specifies the columns to retrieve. It is executed after the filtering (WHERE) and grouping (GROUP BY) operations.

Example:
sql
Copy code
SELECT Name, Salary FROM Employees;
This specifies that only the Name and Salary columns should be retrieved.

DISTINCT:
The DISTINCT keyword removes duplicate rows from the result set. It is applied after the SELECT clause but before ORDER BY.

Example:
sql
Copy code
SELECT DISTINCT Department FROM Employees;
This ensures that only unique departments are retrieved.

ORDER BY:
The ORDER BY clause sorts the result set based on one or more columns. The sorting can be ascending (ASC, the default) or descending (DESC).

Example:
sql
Copy code
SELECT Name, Salary FROM Employees ORDER BY Salary DESC;
This query orders the employees by salary in descending order.

LIMIT / OFFSET:
The LIMIT clause (or OFFSET) restricts the number of rows returned by the query. It is often used for pagination.

Example:
sql
Copy code
SELECT * FROM Employees LIMIT 10;
This query fetches only the first 10 rows from the Employees table.


.. code:: ipython3

    pip install xelatex


.. parsed-literal::

    Note: you may need to restart the kernel to use updated packages.
    

.. parsed-literal::

    ERROR: Could not find a version that satisfies the requirement xelatex (from versions: none)
    ERROR: No matching distribution found for xelatex
    





