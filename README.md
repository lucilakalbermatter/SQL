# Coding SQL

## Commands used:
-   CREATE
-   ALTER
-   DROP
-   TRUNCATE
-   RENAME

<br>

### Code:
temporaryadmin@C02G10FXML86 ~ % psql

psql (14.1)

Type "help" for help.

  

temporaryadmin=# CREATE DATABASE "Digital Career Institute";

CREATE DATABASE

temporaryadmin=# ALTER DATABASE "Digital Career Institute" RENAME TO dci;

ALTER DATABASE

temporaryadmin=# \q

temporaryadmin@C02G10FXML86 ~ % psql dci

psql (14.1)

Type "help" for help.

  

dci=# CREATE SCHEMA students;

CREATE SCHEMA

dci=# CREATE SCHEMA courses;

CREATE SCHEMA

dci=# CREATE SCHEMA partners;

CREATE SCHEMA

dci=# CREATE SCHEMA sales;

CREATE SCHEMA

dci=# SET search_path TO students, courses, partners, sales;

SET

dci=# CREATE TABLE students.studentDetails;

ERROR:  syntax error at or near ";"

LINE 1: CREATE TABLE students.studentDetails;

^

dci=# CREATE TABLE students.studentsDetails (

dci(# firstName varchar(80), lastName varchar(80));

CREATE TABLE

dci=# CREATE TABLE students.studentMarks( id_student int, mark varchar(80));

CREATE TABLE

dci=# CREATE TABLE courses.coursesDetails (course_name varchar(80), startDate date);

CREATE TABLE

dci=# CREATE TABLE courses.teacherDetails (teacher_id int, name varchar(80));

CREATE TABLE

dci=# CREATE TABLE partners.partnerDetails (first_name varchar(80), last_name varchar(80));

CREATE TABLE

dci=# CREATE TABLE partners.department( department_id int, name varchar(80));

CREATE TABLE

dci=# CREATE TABLE sales.customers ( customer_id int, first_name varchar(80), last_name varchar(80));

CREATE TABLE

dci=# CREATE TABLE sales,orders ( order_id int, shipped_date date);

ERROR:  syntax error at or near ","

LINE 1: CREATE TABLE sales,orders ( order_id int, shipped_date date)...

^

dci=# dci=# CREATE TABLE.orders ( order_id int, shipped_date date);

CREATE TABLE

dci=# INSERT INTO studentDetails VALUES ('Karl', 'Marx');

ERROR:  relation "studentdetails" does not exist

LINE 1: INSERT INTO studentDetails VALUES ('Karl', 'Marx');

^

dci=# INSERT INTO students.studentsDetails VALUES ('Karl', 'Marx');

INSERT 0 1

dci=# INSERT INTO students.studentsDetails VALUES ('John', 'Lennon');

INSERT 0 1

dci=# INSERT INTO students.studentsDetails VALUES ('Freddy', 'Mercury');

INSERT 0 1

dci=# INSERT INTO students.studentsDetails VALUES ('Ed', 'Sheeran');

INSERT 0 1

dci=# INSERT INTO students.studentMarks VALUES (1,90);

INSERT 0 1

dci=# INSERT INTO students.studentMarks VALUES (2,85);

INSERT 0 1

dci=# INSERT INTO students.studentMarks VALUES (3,70);

INSERT 0 1

dci=# INSERT INTO students.studentMarks VALUES (4,80);

INSERT 0 1

dci=# INSERT INTO courses.coursesDetails VALUES ('Java', '08-03-2022');

INSERT 0 1

dci=# INSERT INTO courses.coursesDetails VALUES ('Python', '10-04-2022');

INSERT 0 1

dci=# INSERT INTO courses.coursesDetails VALUES ('Web_Design', '15-05-2022');

ERROR:  date/time field value out of range: "15-05-2022"

LINE 1: ...INTO courses.coursesDetails VALUES ('Web_Design', '15-05-202...

^

HINT:  Perhaps you need a different "datestyle" setting.

dci=# INSERT INTO courses.coursesDetails VALUES ('Web_Design', '05-15-2022');

INSERT 0 1

dci=# INSERT INTO courses.coursesDetails VALUES ('Marketing', '06-04-2022');

INSERT 0 1

dci=# INSERT INTO courses.teacherDetails VALUES (54, 'Marie');

INSERT 0 1

dci=# INSERT INTO courses.teacherDetails VALUES (67, 'Luke');

INSERT 0 1

dci=# INSERT INTO courses.teacherDetails VALUES (72, 'Tom');

INSERT 0 1

dci=# INSERT INTO courses.teacherDetails VALUES (85, 'Steve');

INSERT 0 1

dci=# INSERT INTO partners.partnerDetails VALUES ('Mike', 'Tesla'),('George','Waschin'),('Emy','Kalb'),('Mai','Tant');

INSERT 0 4

dci=# dci=# INSERT INTO partners.partnerDetails VALUES (1, 'Sales'),(2,'Marketing'),(3,'IT'),(4,'Logistic');

INSERT 0 4

dci=# INSERT INTO sales.customers VALUES (55,'Peter','Pan'),(69,'Martin','Turi'),(71,'Mike','Lander'),(88,'Ivon','Dorkz');

INSERT 0 4

dci=# INSERT INTO sales.customers VALUES (02,'01-20-2022'),(05,'02-03-2022'),(10,'02-07-2022'),(15, '02-09-2022');

INSERT 0 4

dci=# ALTER TABLE students.studentDetails RENAME TO studentInfo

dci-# ;

ERROR:  relation "students.studentdetails" does not exist

dci=# ALTER TABLE students.studentsDetails RENAME TO studentInfo ;

ALTER TABLE

dci=# ALTER TABLE students.studentInfo RENAME TO studentsDetails;

ALTER TABLE

dci=# ALTER TABLE partners.department RENAME TO partners.department_id;

ERROR:  syntax error at or near "."

LINE 1: ALTER TABLE partners.department RENAME TO partners.departmen...

^

dci=# ALTER TABLE partners.department RENAME TO department_id;

ALTER TABLE

dci=# DROP partners.department_id;

ERROR:  syntax error at or near "partners"

LINE 1: DROP partners.department_id;

^

dci=# DROP TABLE partners.department_id;

DROP TABLE

dci=# TRUNCATE TABLE courses.teacherDetails;

TRUNCATE TABLE

dci=#
