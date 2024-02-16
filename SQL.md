# Dababase: 
    store large data:
    features like security, scalability
    Easier to insert, update or delete data

1- SQL (Structured Query Language):
   relation data bases
   MySQL, Oracle, PostgreSQL etc.
   store data in the form of table
2- No-SQL
   Non Relational Database
   (data store in document, key-value-pair, graphs)
   MongoDB, Cassandra, Neo4j

# DBMS:
database management system
(a layer on the data base)
# Schema 
   columns called schema;
# Tuple
   rows called tuple

# MySQL server & MySQL workbench
[Download MySQL](https://dev.mysql.com/downloads/installer/)

# SQL :
   CREATE DATABASE COLLEGE;
   DROP DATABASE XYZ_COMPANY;
   USE COLLEGE

# 1_talbe :
   CREATE TABLE : (
      CLM_NAME1 DATATYPE CONSTRAIN,
      CLM_NAME2 DATATYPE CONSTRAIN,
      CLM_NAME3 DATATYPE CONSTRAIN,
   )

# Show Tables :
   select * from tableName;
# Database Queries :
   CREATE DATABASE db_name;
   CREATE DATABASE IF NOT EXISTS  db_name;

   DROP DATABASE db_name;
   DROP DATABASE IF EXISTS db_name;

   SHOW DATABASES;
   SHOW TABLES;
# Constraints :
<!-- Rules for data in the table -->
   NOT NULL 
   UNIQUE
   DEFAULT
   CHECK
   PRIMARY KEY :
   FOREIGN KEY :
   FOREIGN KEY (t-id) references techer(id)
# Table Queries :
   CREATE
   INSERT
   UPDATE :
      <!-- 
      update users
      set followers = 600
      where age = 16; -->
   ALTER
   TRUNCATE
   DELETE :
      <!--
      delete from users
      where age = 13;
      select * from users; -->
# Data Types

   char (string 0-255 fixed lenght) CHAR(50)
   varchar //
   blob (string 0 - 65535) can store binary large object.
   int  (-2, 147, 483, 648 to 2, 147, 483, 647)
   tinyint (-128 to 127)
   bigint integer()
   bit(2)  range from 1 to 64;
   float   precision 23 digits
   double 24-53 digits
   boolean
   date
   year 4digits (1901 to 2155)

   unsigned


   <!-- insert into users (id, name, age, email, followers, following) values
(1, "adam",18, "adam@yahoo.in", 123,145),
(2, "bob", 19, "bob123@gmail.com", 200, 200),
(3, "casey", 20, "casey@gmail.com", 300, 306),
(4, "donald", 23, "donald@gmail.com", 200, 105);

insert into users (id, email) values
(2, "adam@yahoo.in");


select id, name, age, email, city, address, followers, following from users; -->
<!-- select * from users;
select distinct age from users; -->


# Clause 
Select col1, col2, From table_name;
# 1_where
Exp. : 
      <!-- select * from users where age < 20;
select name, age
from users
where age >= 20;

select email, id, name, age, followers
from users 
where followers >= 200; -->


   i) Arithmetic Operators
      where age+1 =18;
   ii) Comparison Operators
      =, !=, <=, >=
   iii)Logical Operators
      AND, OR, NOT, IN BETWEEN, ALL, LIKE, ANY
   iv)Bitwise Operators:
      & (bitwise AND), | (bitwise OR)

distict
AND : (to check for both conditions to be true)
   <!-- select * from users 
   where age <= 15 and followers > 200 and id > 101; -->
OR : (to chek for the one of the condition to be true)
   <!-- select * from users 
   where age <= 17 or followers > 300 ; -->
BETWEEN (select for given range) :
   <!-- select * from users
   where age between 16 and 20; -->
IN (match any value in the list):
   <!-- select id, name , age, email from  users
   where email in ("kumar@yahoo.com","casey@yahoo.com","anil@gmail.com","kumar@yahoo.com", "abc.gmail.com"); -->
   <!-- where age in (13, 16); -->
NOT (to negate the given condition)

# Limit Clause :
   select * from users 
   -- limit 5;-- 
   -- limit 3;
   where age in (13,14,15)
   limit 3;


# Order by Clause :
   select col_1, col_2 from tbl_name
   order by col_name asc;
   
   ASC
   DESC


# Aggregate Functions :

count() :
   select count(age) from users;
   select count(name) from users;
max()
min()
sum() :
   select sum(age) from users;
avg()

   <!-- select max(age) from users;
   select min(age) from users;
   select count(age) from users;
   select count(name) from users;
   select sum(age) from users;
   select avg(age) from  users;
   select avg(followers) from users;
   select sum(followers) from users; -->


# Group By Clause :
<!-- Groups rows that have the same values into summary rows. It collects data from multiple records and group the result by one or more column. -->
   -- group by ;
   select age, count(id) from users
   group by age;

# Having Clause :
      <!-- Similar to Where i.e. applies some condition on rows. But it is used when we want to apply any condition after grouping. -->
      select age, max(followers) from users
      group by age 
      having max(followers) > 300;


#  General Order :
   select
   from
   where
   group by
   having
   order by



# Alter Table: 
1-    ADD Column
      ALTER TABLE Table_name
      ADD COLUMN column_name datatype constraint;

2-    DROP Column
      ALTER TABLE Table_name;
      DROP COLUMN column_name;
      <!-- alter table users
      drop column city; -->
3-    Rename Table
      ALTER TABLE tbl_name
      RENAME TO new_tbl_name 
      <!-- alter table users
      rename to subscribers; -->
4-    Change Column Name :
      ALTER TABLE  table_name
      CHANGE COLUMN old_name new_name new_datatype new_constraint;
      <!-- alter table users
      change column followers subscribers int not null; -->
5-    Modify Column (modify datatype/constraint)
      ALTER TABLE table_name
      MODIFY col_name new_datatype new_constraint

# Truncate Table tbl_name


# ERROR (1175) :
   set sql_safe_updates = 0;  