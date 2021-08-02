# SQL - Structured Query Language

### What is data?

1) Facts collected together for reference or analysis.
2) Example -- facts related to you like your name, age, height, weight, etc. are some exmaple of data. Even images, files and PDFs are considered as data.

------------------------------------------------------------------------------------------------------

### Data vs Information

1) Data that has been convereted into a more useful or intelligible form. Data by itself is just a raw unit of information, but only after further processing or analysis does the data become more useful and meaningful, and that is when its called information.
2) Your score is your Math exam in first semester -- Data or information? it is data.
3) The complete class's marks would be a collection of these numbers. By itself its not very meaningful, its just a bunch of numbers. But when we do some aggregations, like suppose finding the average marks , we can understand how the class performed collectively. if the average was say 60/100, a possible insight is that the exam was difficult and that's why it was a low scoring one.

------------------------------------------------------------------------------------------------------

### What is a Database?

1) Set of related data organized in a way that it can be easily stored, changed and accessed at any time.
2) Let’s consider an example – Netflix. As per my understanding, Netflix has database for its movies and tv shows, and it should have another one for the login/credentials details of the users and the movies/tv shows that they have been watching. After doing some analysis and modeling, it also recommends movies based on your watched history. 

---------------------------------------------------------------------------------------------------

### What is a Database Management System?

1) System that manages the storage and retrieval of data from databases.
2) It is a collection of programs which enables its users to access database, manipulate data, reporting and representation of data.

---------------------------------------------------------------------------------------------------

### What is a Database Table?

1) Collection of related data held in a table format within a database. Tables are database objects that contain the data in a database. A database most often contains one or more tables. Each table is identified by a name (e.g. "Customers" or "Orders"). Tables contain rows and columns
2) Consists of columns and rows.
3) A column is a set of data values of a particular type. A column is also called an attribute or fields.
4) A row is a single set of data values of all attributes/columns. They are also called records or tuple.

---------------------------------------------------------------------------------------------------

### SQL 

1) Structred Query Language
2) The language that is commonly used to deal with databases is SQL. It let's you access and manipulate databases.
3) And to understand SQL, we first need to know what the Q in SQL means. A query is really a question or request for data. For example, "tell me how how many books there are on computer Programming in the University library".

```

SELECT * FROM university.library 
WHERE book_type = 'Computer Programming';

```

---------------------------------------------------------------------------------------------------

### What all can SQL do?

1) SQL can execute queries against a database.
2) SQL can retrieve data from a database.
3) SQL can insert records in a database.
4) SQL can update records in a database.
5) SQL can delete records from a database.
6) SQL can create new databases.
7) SQL can create new tables in a database.
8) SQL can set permissions on tables.

---------------------------------------------------------------------------------------------------

### DBMS Keys

A DBMS key is an column or set of columns which helps you to uniquely identify a row in a table.

#### Types of DBMS Keys

1) Super Key - A single key or a group of multiple keys that can uniquely identify tuples in a table
2) Candidate Key - A Subset of Super keys and is devoid of any unnecessary attributes that are not important for uniquely identifying tuples. Candidate key for the following data is ID and Email ID.
3) Primary Key - The Candidate key selected by the database administrator to uniquely identify tuples in a table. ID would be primary key for the following data 
      
        1) Should be unique -- cannot ever repeat
        2) Should be not null -- Will always need a value

4) Alternate key or Secondary key - The Candidate keys which are not the Primary Key. Email ID would be the alternate key.
5) Foreign Key - An attribute which is a Primary Key in its parent table, but is included as an attribute in another host table. Id in the Second Table would be the foreign key.
6) Composite key - Key that consists of two or more attributes that uniquely identify any record but individually the attributes are not keys. 

---------------------------------------------------------------------------------------------------

### Database Schema

A database schema is the skeleton structure that represents the logical view of the entire database. It defines how the data is organized and how the relations among them are associated. It formulates all the constraints that are to be applied on the data.

---------------------------------------------------------------------------------------------------

### Postgresql Installation

Download - https://www.postgresql.org/download/

prerequisites

1) Run SQL Shell
2) Copy data from file code.txt
3) paste in SQL Shell

---------------------------------------------------------------------------------------------------

### Postgresql Commands 

1) SELECT -- It is used to choose the columns you want to view and you can also select any columns.
2) FROM -- It is used to choose the table from which you want the data.

            SELECT column_name1, column_name2, .., column_nameX 
            FROM schema_name.table_name;


![alt text](https://github.com/mohit11R/SQl-Notes/blob/main/select_from.PNG?raw=true)

3) LIMIT -- It is used to limit the amount of records returned as per a query.

            SELECT * 
            FROM public.customers 
            LIMIT 10;
            
            
![alt text](https://github.com/mohit11R/SQl-Notes/blob/main/limit.PNG?raw=true)


4) DISTINCT -- IT is used to find the list of unique values of the column mentioned in the DISTINCT portion of the query. In case of multiple columns, DISTINCT returns a list of unique values of the combinations of the columns.
            
            SELECT DISTINCT column_name1, column_name2, .., column_nameX 
            FROM schema_name.table_name;


![alt text](https://github.com/mohit11R/SQl-Notes/blob/main/dis.PNG?raw=true)


5) COUNT -- Unlike all the keywords we have discussed so far, COUNT is a function. It expects an input, does some processing, and returns an output. COUNT specifically expects only and exactly one input. It returns the count of values in a column.
                  
                  SELECT COUNT(column_name)
                  FROM schema_name.table_name;

![alt text](https://github.com/mohit11R/SQl-Notes/blob/main/count.PNG?raw=true)


We can also use DISTINCT in COUNT FUNCTION 

COUNT DISTINCT combination is used to first find the distinct values in a column and then find the count of it
                  
                  SELECT COUNT(DISTINCT column_name)
                  FROM schema_name.table_name;


![alt text](https://github.com/mohit11R/SQl-Notes/blob/main/count_dis.PNG?raw=true)


##### Why COUNT(DISTINCT *) is incorrect?

1) COUNT(*) works in SQL and DISTINCT * works too. 
2) But, COUNT(DISTINCT *) doesn’t work. Logical explanation for that (although its not as per google. Google just gives a syntactical definition) is that while solving the bracket first, the DISTINCT * returns a list of columns which have had their duplicate tuples remove. So, COUNT, which expects only one parameter as input, now has more than one 
parameter in the form of the multiple columns. Hence, it throws an error


 
 6) **Where** -- filter rows returned by a SELECT statement.

```
SELECT column_name 
FROM schema_name.table_name 
WHERE column_nameX operator value;
```

7) **Operators** 

      1) =
      2) <
      3) >
      4) <=
      5) >=
      6) <>
      7) !=
      8) Between value1 AND value2
      9) LIKE 'value'
      10) IN (value1,value2,...,valueX)
      11) AND, OR, NOT

8) **LIKE in conjunction with Wildcards** 

```
SELECT *
FROM public.customers 
WHERE first_name LIKE ‘Jas%';
```

9) Types of Wildcards

      1) % -- Represents zero or more characters
      2) _ -- Represents a single character

      ```
      WHERE first_name LIKE 'ro%'; -- rohan, ro
      WHERE first_name LIKE '%ro'; -- wipro, ro
      WHERE first_name LIKE '%ro%'; -- trophy,road, electro, ro
      WHERE first_name LIKE '_ro%'; -- iron, Fro
      WHERE first_name LIKE 'ro_%_'; -- roam,round
      ```
      
      
10) **LOWER and UPPER in WHERE** 

```
SELECT *
FROM public.customers 
WHERE UPPER(first_name) LIKE ‘JAS%';
```
```
ELECT *
FROM public.customers 
WHERE LOWER(first_name) LIKE ‘JAS%';
```


11) **IS NULL and IS NOT NULL**

```
SELECT *
FROM schema_name.table_name 
WHERE column_nameX IS NULL;
```
```
SELECT *
FROM schema_name.table_name 
WHERE column_nameX IS NOT NULL;
```
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
12) **Aggregate Functions** 

      1) SUM -- It returns the total summed values (Non-NULL) in a set.
      2) AVG -- It returns the average value of an expression.
      3) MIN -- It returns the minimum (lowest) value in a set.
      4) MAX -- 	It returns the maximum (highest) value in a set.
      5) COUNT -- It returns the number of rows, including rows with NULL values in a group.
      6) FIRST -- It returns the first value of an expression.
      7) LAST -- It returns the last value of an expression.

```
SELECT SUM(column1) , AVG(column1), MIN(column1),MAX(column1)
FROM schema_name.table_name 

```
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
13) **Aliases**

Aliases are used to give a table, or a column in a table, a temporary name.

```
SELECT MAX(sale_date) AS max_sale_date, 
MIN(sale_date) AS min_sale_date 
FROM public.sales;
```
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
14) **GROUP BY**

The GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country".

The GROUP BY statement is often used with aggregate functions (COUNT(), MAX(), MIN(), SUM(), AVG()) to group the result-set by one or more columns.

```
SELECT column1, SUM(column2) 
FROM schema_name.table_name 
WHERE condition 
GROUP BY column1;
```

**Point to remember** – Once you have done a GROUP BY on a column (or multiple columns), only those are accessible for selection in SELECT without aggregation. Any other columns would need some form of aggregation to be used in SELECT.


**Conditions of GROUP BY**

   1) If column is mentioned in SELECT list excluding the ones used in aggregations, it has to be mentioned in the GROUP BY list.
      
   2) If column is mentioned in GROUP BY list, it is not compulsory to mention it in the SELECT list, though if you do that, you won’t know which record the aggregated value is for.
      
   3) Some DBMS (SQL Servers) allow the alias name to be used in the GROUP BY list.
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

15) **HAVING**

The HAVING clause was added to SQL because the WHERE keyword cannot be used with aggregate functions.

```
SELECT column1, column2, aggregation(column3) 
FROM schema_name.table_name  
GROUP BY column1, column2 
HAVING aggregation(column) operator value 
```

**Point to remember** -- WHERE only works for rows and not for the whole table, as shown in previous Poll. So, we cant perform aggregations in WHERE. To use Aggregations filters, we will need HAVING. HAVING is used to remove the groups (created as per GROUP BY) completely from the data. 



---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

16) **JOINS**

**Types of Joins**

1) INNER JOIN or JOIN
2) LEFT JOIN or LEFT OUTER JOIN
3) RIGHT JOIN or RIGHT OUTER JOIN
4) FULL JOIN or FULL OUTER JOIN
5) SELF JOIN (conceptual)
6) CROSS JOIN  (conceptual)

```
Syntax for Joins

SELECT table1.column1, table1.column2, table2.column1, table2.column2
FROM schema_name.table1
____ JOIN schema_name.table2 
ON table1.columnX operator table2.column;

```
**ON vs WHERE** 

1) ON and WHERE would always give the same result in case of INNER JOIN.
2) In case of any other JOIN, it isn’t necessary that the two queries give the same result. It could vary, as explained in the attached excel.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


1) **Inner Joins**

The INNER JOIN keyword selects records that have matching values in both tables.

```
SELECT c.first_name, SUM(s.sale_amount) 
FROM public.customers AS c
INNER JOIN public.sales AS s
ON c.id = s.customer_id
WHERE c.age > 35 
GROUP BY c.first_name 
HAVING COUNT(s.sale_id) < 6 
LIMIT 5;
```

2) **Left Join or Left Outer Join**

The LEFT JOIN keyword returns all records from the left table (table1), and the matching records from the right table (table2). The result is 0 records from the right side, if there is no match.

The LEFT JOIN keyword returns all records from the left table (Customers), even if there are no matches in the right table (Orders).


```
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```

3) **Right Join or Right Outer Join**

The RIGHT JOIN keyword returns all records from the right table (table2), and the matching records from the left table (table1). The result is 0 records from the left side, if there is no match.

The RIGHT JOIN keyword returns all records from the right table (Employees), even if there are no matches in the left table (Orders).

```
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```


4) **Full Join or Full Outer Join**

The FULL OUTER JOIN keyword returns all records when there is a match in left (table1) or right (table2) table records.


The FULL OUTER JOIN keyword returns all matching records from both tables whether the other table matches or not. So, if there are rows in "Customers" that do not have matches in "Orders", or if there are rows in "Orders" that do not have matches in "Customers", those rows will be listed as well.

```
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name
WHERE condition;
```
5) **SELF Join**
6) **Cross Join**













