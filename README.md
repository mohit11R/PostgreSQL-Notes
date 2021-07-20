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


4) DISTINCT - IT is used to find the list of unique values of the column mentioned in the DISTINCT portion of the query. In case of multiple columns, DISTINCT returns a list of unique values of the combinations of the columns.
            
            SELECT DISTINCT column_name1, column_name2, .., column_nameX 
            FROM schema_name.table_name;


![alt text](https://github.com/mohit11R/SQl-Notes/blob/main/dis.PNG?raw=true)


5) COUNT - Unlike all the keywords we have discussed so far, COUNT is a function. It expects an input, does some processing, and returns an output. COUNT specifically expects only and exactly one input. It returns the count of values in a column.
                  
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
2) But, COUNT(DISTINCT *) doesn’t work. Logical explanation for that (although its not as per google. Google just gives a syntactical definition) is that while solving the  
bracket first, the DISTINCT * returns a list of columns which have had their duplicate tuples remove. So, COUNT, which expects only one parameter as input, now has more than one 
parameter in the form of the multiple columns. Hence, it throws an error

 






























