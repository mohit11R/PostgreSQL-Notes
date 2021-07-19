# SQL - Structure Query Language

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





























