Programming 12,13



Database Programming with SQL
12-1: INSERT Statements
Practice Activities

Objectives
• Give examples of why it is important to be able to alter the data in a database
• Construct and execute INSERT statements that insert a single row using a VALUES clause
• Construct and execute INSERT statements that use special values, null values, and date values
• Construct and execute INSERT statements that copy rows from one table to another using a subquery

Vocabulary
Identify the vocabulary word for each definition below.
- Someone doing “real work” with the computer, using it as a
means rather than an end
End user
- Consists of a collection of DML statements that form a logical unit of work.
transaction
- Fully and clearly expressed; leaving nothing implied
explicit
- Adds a new row to a table
insert

Try It / Solve It

Students should execute DESC tablename before doing INSERT to view the data types for each column. VARCHAR2 data-type entries need single quotation marks in the VALUES statement.

1. Give two examples of why it is important to be able to alter the data in a database.

- It is important to be able to alter data in a database in order to ensure the most relevant data is inputted/included , and that any duplicates or errors can be addressed immediately. 

2. DJs on Demand just purchased four new CDs. Use an explicit INSERT statement to add each CD to the copy_d_cds table. After completing the entries, execute a SELECT * statement to verify your work.

 

 

INSERT INTO copy_d_songs 
SELECT id, title, duration, type_code
FROM song_requests

 
INSERT INTO copy_d_clients (client_number, first_name, last_name, phone, email) 
VALUES (6655, 'Ayako’ , ‘Dahish’ , 3608859030 , ‘dahisha@harbor.net’); 
INSERT INTO copy_d_clients (client_number, first_name, last_name, phone, email) 
VALUES (6689, 'Nick', ‘Neuville’ , ‘9048953049’ , ‘nnicky@charter.net’);

 
INSERT INTO copy_d_events (event_id, client_id, event_name, event_date, cost) VALUES (301, 201, 'Fall Football Party', '2024-11-10', NULL); 
INSERT INTO copy_d_events (event_id, client_id, event_name, event_date, cost) VALUES (302, 202, 'Sixties Theme Party', '2024-11-15', NULL);
6. Create a table called rep_email using the following statement:
CREATE TABLE rep_email (
id NUMBER(3) CONSTRAINT rel_id_pk PRIMARY KEY,
first_name VARCHAR2(10),
last_name VARCHAR2(10),
email_address VARCHAR2(10))

Populate this table by running a query on the employees table that includes only those employees who are REP’s.

CREATE TABLE rep_email (
    id NUMBER(3) CONSTRAINT rel_id_pk PRIMARY KEY,
    first_name VARCHAR2(10),
    last_name VARCHAR2(10),
    email_address VARCHAR2(10)
);

Database Programming with SQL
12-2: Updating Column Values and Deleting Rows
Practice Activities

Objectives
• Construct and execute an UPDATE statement
• Construct and execute a DELETE statement
• Construct and execute a query that uses a subquery to update and delete data from a table
• Construct and execute a query that uses a correlated subquery to update and delete from a table
• Explain how foreign-key and primary-key integrity constraints affect UPDATE and DELETE
statements
• Explain the purpose of the FOR UPDATE Clause in a SELECT statement

Vocabulary
Identify the vocabulary word for each definition below.

-	Modifies existing rows in a table
- UPDATE
-	retrieves information from one table & uses the information to
update another table
- SUBQUERY
-	Ensures that the data adheres to a predefined set of rules
- INTEGRITY CONSTRAINT
-	deletes information on a linked table based on what was deleted
on the other table
- ON DELETE CASCADE
-	Removes existing rows from a table
 - DELETE

Try It / Solve It
NOTE: Copy tables in this section do not exist
If any change is not possible, give an explanation as to why it is not possible.

1. Monique Tuttle, the manager of Global Fast Foods, sent a memo requesting an immediate change in prices. The price for a strawberry shake will be raised from $3.59 to $3.75, and the price for fries will increase to $1.20. Make these changes to the copy_f_food_items table.

UPDATE copy_f_food_items 
SET price = 3.75 
WHERE LOWER(description) = 'strawberry shake'; 

UPDATE copy_f_food_items 
SET price = 1.20 
WHERE LOWER(description) = 'fries';

2. Bob Miller and Sue Doe have been outstanding employees at Global Fast Foods. Management has decided to reward them by increasing their overtime pay. Bob Miller will receive an additional $0.75 per hour and Sue Doe will receive an additional $0.85 per hour. Update the copy_f_staffs table to show these new values. (Note: Bob Miller currently doesn’t get overtime pay. What function do you need to use to convert a null value to 0?)

UPDATE copy_f_staffs 
SET overtime_pay = NVL(overtime_pay, 0) + 0.75 
WHERE LOWER(first_name) = 'bob' AND LOWER(last_name) = 'miller';

UPDATE copy_f_staffs 
SET overtime_pay = NVL(overtime_pay, 0) + 0.85 
WHERE LOWER(first_name) = 'sue' AND LOWER(last_name) = 'doe';  

INSERT INTO copy_f_orders(order_number,order_date,order_total,cust_id,staff_id)
VALUES (101, 1, '2024-11-10', 25.50);
 
INSERT INTO copy_f_customers (customer_id, customer_name, contact_info) 


5. Sue Doe has been an outstanding Global Foods staff member and has been given a salary raise. She will now be paid the same as Bob Miller. Update her record in copy_f_staffs.

UPDATE copy_f_staffs 
SET salary = (SELECT salary FROM copy_f_staffs WHERE LOWER(first_name) = 'bob' AND LOWER(last_name) = 'miller') 
WHERE LOWER(first_name) = 'sue' AND LOWER(last_name) = 'doe';

6. Global Fast Foods is expanding their staff. The manager, Monique Tuttle, has hired Kai Kim. Not all information is available at this time, but add the information shown here

INSERT INTO copy_f_staffs(id,first_name,last_name,birthdate,salary,overtime_rate, ,staff_type) VALUES(25,'Kai','Kim',TO_DATE('03-Nov-1988','fmdd-Mon-yyyy'),6.75,'Order Taker');

7. Now that all the information is available for Kai Kim, update his Global Fast Foods record to include the following: Kai will have the same manager as Sue Doe. He does not qualify for overtime. Leave the values for training, manager budget, and manager target as null.

8. Execute the following SQL statement. Record your results.
DELETE from departments
WHERE department_id = 60;

9. Kim Kai has decided to go back to college and does not have the time to work and go to school. Delete him from the Global Fast Foods staff. Verify that the change was made.

10. Create a copy of the employees table and call it lesson7_emp;
Once this table exists, write a correlated delete statement that will delete any employees from the lesson7_employees table that also exist in the job_history table


Database Programming with SQL
12-3: DEFAULT Values, MERGE, and Multi-Table Inserts
Practice Activities

Objectives
• Understand when to specify a DEFAULT value
• Construct and execute a MERGE statement
• Construct and execute DML statements using SUBQUERIES
• Construct and execute multi-table inserts

Try It / Solve It
1. When would you want a DEFAULT value?
2. Currently, the Global Foods F_PROMOTIONAL_MENUS table START_DATE column does not have SYSDATE set as DEFAULT. Your manager has decided she would like to be able to set the starting date of promotions to the current day for some entries. This will require three steps:
a. In your schema, Make a copy of the Global Foods F_PROMOTIONAL_MENUS table using the following SQL statement:
CREATE TABLE copy_f_promotional_menus
AS (SELECT * FROM f_promotional_menus)
b. Alter the current START_DATE column attributes using:
ALTER TABLE copy_f_promotional_menus
MODIFY(start_date DATE DEFAULT SYSDATE)
c. INSERT the new information and check to verify the results.
INSERT a new row into the copy_f_promotional_menus table for the manager’s new
promotion. The promotion code is 120. The name of the promotion is ‘New Customer.’ Enter DEFAULT for the start date and '01-Jun-2005' for the ending date. The giveaway is a 10% discount coupon. What was the correct syntax used?


3. Allison Plumb, the event planning manager for DJs on Demand, has just given you the following list of CDs she acquired from a company going out of business. She wants a new updated list of CDs in inventory in an hour, but she doesn’t want the original D_CDS table changed. Prepare an updated inventory list just for her.
a. Assign new cd_numbers to each new CD acquired.
b. Create a copy of the D_CDS table called manager_copy_d_cds. What was the correct syntax used?
c. INSERT into the manager_copy_d_cds table each new CD title using an INSERT statement. Make up one example or use this data:
20, 'Hello World Here I Am', 'Middle Earth Records', '1998' What was the correct syntax used?
d. Use a merge statement to add to the manager_copy_d_cds table, the CDs from the original table. If there is a match, update the title and year. If not, insert the data from the original table. What was the correct syntax used?
4. Run the following 3 statements to create 3 new tables for use in a Multi-table insert statement. All 3 tables should be empty on creation, hence the WHERE 1=2 condition in the WHERE clause.
CREATE TABLE sal_history (employee_id, hire_date, salary)
AS SELECT employee_id, hire_date, salary
FROM employees
WHERE 1=2;
CREATE TABLE mgr_history (employee_id, manager_id, salary)
AS SELECT employee_id, manager_id, salary
FROM employees
WHERE 1=2;
CREATE TABLE special_sal (employee_id, salary)
AS SELECT employee_id, salary
FROM employees
WHERE 1=2;
Once the tables exist in your account, write a Multi-Table insert statement to first select the
employee_id, hire_date, salary, and manager_id of all employees. If the salary is more than
20000 insert the employee_id and salary into the special_sal table. Insert the details of
employee_id, hire_date, and salary into the sal_history table. Insert the employee_id,
manager_id, and salary into the mgr_history table.
You should get a message back saying 39 rows were inserted. Verify you get this message and verify you have the following number of rows in each table:
Sal_history: 19 rows
Mgr_history: 19 rows
Special_sal: 1


Database Programming with SQL
13-1: Creating Tables
Practice Activities

Objectives
• List and categorize the main database objects
• Review a table structure
• Describe how database schema objects are used by the Oracle database

Vocabulary
Identify the vocabulary word for each definition below.

-	Created and maintained by the Oracle Server and contains
information about the database

-	A collection of objects that are the logical structures that directly
refer to the data in the database

-	Specifies a preset value if a value is omitted in the INSERT
statement

-	Stores data; basic unit of storage composed of rows
and columns

-	Command use to make a new table


Try It / Solve It
1. Complete the GRADUATE CANDIDATE table instance chart. Credits is a foreign-key column referencing the requirements table.

2. Write the syntax to create the grad_candidates table.

3. Confirm creation of the table using DESCRIBE.

4. Create a new table using a subquery. Name the new table your last name -- e.g., smith_table. Using a subquery, copy grad_candidates into smith_table.

5. Insert your personal data into the table created in question 4.
6. Query the data dictionary for each of the following:
• USER_TABLES
• USER_OBJECTS
• USER_CATALOG or USER_CAT
In separate sentences, summarize what each query will return.


Database Programming with SQL
13-2: Using Data Types
Practice Activities

Objectives
• Create a table using TIMESTAMP and TIMESTAMP WITH TIME ZONE column data types
• Create a table using INTERVAL YEAR TO MONTH and INTERVAL DAY TO SECOND column
data types
• Give examples of organizations and personal situations where it is important to know to which time zone a date-time value refers
• List and provide an example of each of the number, date, and character data types

Vocabulary
Identify the vocabulary word for each definition below.

-	Allows time to be stored as an interval of years and months

-	When a column is selected in a SQL statement the time is
automatically converted to the user’s timezone

-	Binary large object data up to 4 gigabytes

-	Stores a time zone value as a displacement from Universal

-	Coordinated Time or UCT

-	Allows time to be stored as an interval of days to hours, minutes,
and seconds

-	Character data up to 4 gigabytes

-	Allows the time to be stored as a date with fractional seconds


Try It / Solve It
1. Create tables using each of the listed time-zone data types, use your time-zone and one other in your examples. Answers will vary.
a. TIMESTAMP WITH LOCAL TIME ZONE
b. INTERVAL YEAR TO MONTH
c. INTERVAL DAY TO SECOND
2. Execute a SELECT * from each table
to verify your input.
3. Give 3 examples of organizations and personal situations where it is important to know to which time zone a date-time value refers.

Database Programming with SQL
13-3: Modifying a Table
Practice Activities

Objectives
• Explain why it is important to be able to modify a table
• Explain and provide an example for each of the DDL statements—ALTER, DROP, RENAME,
and TRUNCATE—and the effect each has on tables and columns
• Construct a query and execute the ALTER TABLE commands ADD, MODIFY, and DROP
• Explain and perform a FLASHBACK QUERY on a table
• Explain and perform FLASHBACK table operations
• Track the changes to data over a period of time
• Explain the rationale for using TRUNCATE versus DELETE for tables
• Add a comment to a table using the COMMENT ON TABLE command
• Name the changes that can and cannot be made to modify a column
• Explain when and why the SET UNUSED statement is advantageous

Try It / Solve It
Before beginning the practice exercises, execute a DESCRIBE for each of the following tables: o_employees, o_departments and o_jobs. These tables will be used in the exercises. If they do not exist in your account, create them as follows:

1. Create the three o_tables – jobs, employees, and departments – using the syntax:
CREATE TABLE o_jobs AS (SELECT * FROM jobs);
CREATE TABLE o_employees AS (SELECT * FROM employees);
CREATE TABLE o_departments AS (SELECT * FROM departments);

2. Add the Human Resources job to the jobs table:
INSERT INTO o_jobs (job_id, job_title, min_salary, max_salary)
VALUES('HR_MAN', 'Human Resources Manager', 4500, 5500);

3. Add the three new employees to the employees table:
INSERT INTO o_employees (employee_id, first_name, last_name, email, hire_date,
job_id) VALUES(210, 'Ramon', 'Sanchez', 'RSANCHEZ', SYSDATE, 'HR_MAN');

4. Add Human Resources to the departments table:
INSERT INTO o_departments(department_id, department_name)
VALUES (210,'Human Resources');

You will need to know which columns do not allow null values.

1. Why is it important to be able to modify a table?

2. CREATE a table called Artists.
a. Add the following to the table:
• artist ID
• first name
• last name
• band name
• email
• hourly rate
b. INSERT one artist from the d_songs table.
c. INSERT one artist of your own choosing.
d. Give an example how each of the following may be used on the table that you have created:
1) ALTER TABLE
2) DROP TABLE
3) RENAME TABLE
4) TRUNCATE
5) COMMENT ON TABLE

3. In your o_employees table, enter a new column called “Termination.” The datatype for the new column should be VARCHAR2. Set the DEFAULT for this column as SYSDATE to appear as character data in the format: February 20th, 2003.

4. Create a new column in the o_employees table called start_date. Use the TIMESTAMP WITH LOCAL TIME ZONE as the datatype.

5. Truncate the o_jobs table. Then do a SELECT * statement.
Are the columns still there? Is the data still there?

6. What is the distinction between TRUNCATE, DELETE, and DROP for tables?

7. List the changes that can and cannot be made to a column.

8. Add the following comment to the o_jobs table:
"New job description added"
View the data dictionary to view your comments.

9. Rename the o_jobs table to o_job_description.

10. F_staffs table exercises:
a. Create a copy of the f_staffs table called copy_f_staffs and use this copy table for the
remaining labs in this lesson.
b. Describe the new table to make sure it exists.
c. Drop the table.
d. Try to select from the table.
e. Investigate your recyclebin to see where the table went.
f. Try to select from the dropped table by using the value stored in the OBJECT_NAME column.
You will need to copy and paste the name as it is exactly, and enclose the new name in “ “
(double quotes). So if the dropped name returned to you is
BIN$Q+x1nJdcUnngQESYELVIdQ==$0, you need to write a query that refers to
“BIN$Q+x1nJdcUnngQESYELVIdQ==$0”.
g. Undrop the table.
h. Describe the table.


11. Still working with the copy_f_staffs table, perform an update on the table.
a. Issue a select statement to see all rows and all columns from the copy_f_staffs table;
b. Change the salary for Sue Doe to 12 and commit the change.
c. Issue a select statement to see all rows and all columns from the copy_f_staffs table;
d. For Sue Doe, update the salary to 2 and commit the change.
e. Issue a select statement to see all rows and all columns from the copy_f_staffs table;
f. Now, issue a FLASHBACK QUERY statement against the copy_f_staffs table, so you can see all the changes made.
g. Investigate the result of f), and find the original salary and update the copy_f_staffs table salary column for Sue Doe back to her original salary.
![Uploading image.png…]()
