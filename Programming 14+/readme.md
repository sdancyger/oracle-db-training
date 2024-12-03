Programming 14+

Instructions	
• 14-1 Intro to Constraints; NOT NULL and UNIQUE Constraints
• 14-2 PRIMARY KEY, FOREIGN KEY, and CHECK Constraints
• 14-3 Managing Constraints
• 15-1 Creating Views
• 15-2 DML Operations and Views
• 15-3 Managing Views
• 16-1 Working With Sequences
• 16-2 Indexes and Synonyms
• 17-1 Controlling User Access
• 17-2 Creating and Revoking Object Privileges
• 17-3 Regular Expressions


Database Programming with SQL
14-1: Intro to Constraints; NOT NULL and UNIQUE Constraints
Practice Activities
Objectives
• Define the term "constraint" as it relates to data integrity
• State when it is possible to define a constraint at the column level, and when it is possible at the table level
• State why it is important to give meaningful names to constraints
• State which data integrity rules are enforced by NOT NULL and UNIQUE constraints
• Write a CREATE TABLE statement which includes NOT NULL and UNIQUE constraints at the table and column levels
• Explain how constraints are created at the time of table creation

Vocabulary
Identify the vocabulary word for each definition below.

-	Every value in a column or set of columns (a composite key)
must be unique
--unique constraint
-	For every row entered into the table, there must be a value for
that column
--not null constraint
-	Constraint ensures that the column contains no null values and
uniquely identifies each row of the table
--primary key
-	Specifies a condition for a column that must be true for each row
of data
--check constraint
-	Identifies that table and column in the parent table
--foreign key
-	An integrity constraint that requires every value in a column or set
of columns be unique
-- unique constraint
-	Designates a column (child table) that establishes a relationship
between a primary key in the same table and a different table
(parent table)
--foreign key
-	References one or more columns and is defined separately from
the definitions of the columns in the table
-- table level constraint
-	Database rule.
-- constraint
-	Database rule that references a single column
-- column level constraint
Try It / Solve It
Global Fast Foods has been very successful this past year and has opened several new stores. They need to add a table to their database to store information about each of their store’s locations. The owners want to make sure that all entries have an identification number, date opened, address, and city and that no other entry in the table can have the same email address. Based on this information, answer the following questions about the global_locations table. Use the table for your answers.

1. What is a “constraint” as it relates to data integrity?
-- A constraint is a restriction that is utilized to ensure data remains relevant and correct. 

2. What are the limitations of constraints that may be applied at the column level and at the table level?
-- There are limitations of constraints at both the column level and table level. Column level constraint includes single focus on one column only ; Table level constraint includes not being able to focus on single columns. Table level can also be more complex due to longer SQL length. 

3. Why is it important to give meaningful names to constraints?
-- To be able to comprehend easily and allow for easy ability to make adjustments/updates as needed 
4. Based on the information provided by the owners, choose a datatype for each column. Indicate the length, precision, and scale for each NUMBER datatype.
5. Use “nullable” to indicate those columns that can have null values.

CREATE TABLE global_locations (
    id NUMBER(5) CONSTRAINT global_locations_id_pk PRIMARY KEY NOT NULL,  
    name VARCHAR2(100) NOT NULL,                                         
    date_opened DATE NOT NULL,                                           
    address VARCHAR2(200) NOT NULL,                                      
    city VARCHAR2(50) NOT NULL,                                          
    zip_postal_code VARCHAR2(15) NULL,                                   
    phone VARCHAR2(15) NULL,                                             
    email VARCHAR2(100) CONSTRAINT global_locations_email_uk UNIQUE NULL, 
    manager_id NUMBER(5) NULL,                                            
    emergency_contact VARCHAR2(100) NULL                                  
);

6. Write the CREATE TABLE statement for the Global Fast Foods locations table to define the constraints at the column level.
CREATE TABLE global_locations (
    id NUMBER(5) PRIMARY KEY,
    name VARCHAR2(100) NOT NULL,
    date_opened DATE NOT NULL,
    address VARCHAR2(200) NOT NULL,
    city VARCHAR2(50) NOT NULL,
    zip_postal_code VARCHAR2(15),
    phone VARCHAR2(15),
    email VARCHAR2(100) UNIQUE,
    manager_id NUMBER(5),
    emergency_contact VARCHAR2(100)
);

7. Execute the CREATE TABLE statement in Oracle Application Express.
8. Execute a DESCRIBE command to view the Table Summary information.
DESCRIBE global_locations;
9. Rewrite the CREATE TABLE statement for the Global Fast Foods locations table to define the UNIQUE constraints at the table level. Do not execute this statement
CREATE TABLE global_locations (
    id NUMBER(5) PRIMARY KEY,
    name VARCHAR2(100) NOT NULL,
    date_opened DATE NOT NULL,
    address VARCHAR2(200) NOT NULL,
    city VARCHAR2(50) NOT NULL,
    zip_postal_code VARCHAR2(15),
    phone VARCHAR2(15),
    email VARCHAR2(100),
    manager_id NUMBER(5),
    emergency_contact VARCHAR2(100),
    CONSTRAINT unique_email UNIQUE (email)
);

Database Programming with SQL
14-2: PRIMARY KEY, FOREIGN KEY, and CHECK Constraints
Practice Activities
Objectives
• Define and give an example of PRIMARY KEY, FOREIGN KEY, and CHECK constraints
• Explain the purpose of defining PRIMARY KEY, FOREIGN KEY, and CHECK constraints on a
table
• Demonstrate the creation of constraints at the column level and table level in a CREATE
TABLE statement
• Evaluate a business problem requiring the addition of a PRIMARY KEY and FOREIGN KEY
constraint and write the code to execute the change

Vocabulary
Identify the vocabulary word for each definition below.

-	Allows a foreign key row that is referenced to a primary key row to be deleted
on delete cascade
-	Explicitly defines a condition that must be met
check constraint
-	A column or set of columns that uniquely identifies each row in a table
primary key
-	Constraint ensures that the column contains no null values
not null constraint
-	Allows a child row to remain in a table with null values when a parent record has been deleted
on delete set 
-	Establishes a relationship between the foreign key column and a primary key or unique key in the same table or a different table
Foreign key

Try It / Solve It
1. What is the purpose of a
a. PRIMARY KEY
-- unique identifier that ensures each row is identifiable. 
b. FOREIGN KEY
-- establish connection between two tables
c. CHECK CONSTRAINT
-- ensure data is valid 
2. Using the column information for the animals table below, name constraints where applicable at the table level, otherwise name them at the column level. Define the primary key (animal_id). The license_tag_number must be unique. The admit_date and vaccination_date columns cannot
contain null values.

animal_id NUMBER(6) 
name VARCHAR2(25)
license_tag_number NUMBER(10)
admit_date DATE
adoption_id NUMBER(5),
vaccination_date DATE


animal_id NUMBER(6)  = primary key
license_tag_number NUMBER(10) = unique id
admit_date DATE = not null
vaccination_date DATE = not null


3. Create the animals table. Write the syntax you will use to create the table.

CREATE TABLE animals ( animal_id NUMBER(6) PRIMARY KEY, name VARCHAR2(25), license_tag_number NUMBER(10) UNIQUE, admit_date DATE NOT NULL, adoption_id NUMBER(5), vaccination_date DATE NOT NULL 
);

4. Enter one row into the table. Execute a SELECT * statement to verify your input. Refer to the graphic below for input.

5. Write the syntax to create a foreign key (adoption_id) in the animals table that has a
corresponding primary- key reference in the adoptions table. Show both the column-level and table-level syntax. Note that because you have not actually created an adoptions table, no adoption_id primary key exists, so the foreign key cannot be added to the animals table.

CREATE TABLE animals ( animal_id NUMBER(6) PRIMARY KEY, name VARCHAR2(25), license_tag_number NUMBER(10) UNIQUE, admit_date DATE NOT NULL, adoption_id NUMBER(5) REFERENCES adoptions(adoption_id), vaccination_date DATE NOT NULL 
);

6. What is the effect of setting the foreign key in the ANIMAL table as:
a. ON DELETE CASCADE
--allows for all deletion 
b. ON DELETE SET NULL
-- allows for child table to be null when a parent table is deleted

7. What are the restrictions on defining a CHECK constraint?
-- only able to refer to columns within that table ; subqueries not allowed ; table level 


Database Programming with SQL
14-3: Managing Constraints
Practice Activities
Objectives
• List four different functions that the ALTER statement can perform on constraints
• Write ALTER TABLE statements to add, drop, disable, and enable constraints
• Name a business function that would require a DBA to drop, enable, and/or disable a
constraint or use the CASCADE syntax
• Query the data dictionary for USER_CONSTRAINTS and interpret the information returned

Vocabulary
Identify the vocabulary word for each definition below.

- To deactivate an integrity constraint
-- disable constraint
- Disables dependent integrity constraints
-- cascade 
- To add, modify, or drop columns from a table
-- alter table
- To activate an integrity constraint currently disabled
-- enable constraint
- Removes a constraint from a table
-- drop constraint
- Allows user to delete a column from a table
-- drop column
- Defines the actions the database server takes when a user
attempts to delete or update a key to which existing foreign keys
point
-- cascade constraint

Try It / Solve It
Using Oracle Application Express, click the SQL Workshop tab in the menu bar. Click the Object Browser and verify that you have a table named copy_d_clients and a table named copy_d_events. If you don’t have these tables in your schema, create them before completing the exercises below. Here is how the original tables are related. The d_clients table has a primary key client_number. This has a primary-key constraint and it is referenced in the foreign-key constraint on the d_events table.
1. What are four functions that an ALTER statement can perform on constraints?
-- add, drop, enable, disable
2. Since the tables are copies of the original tables, the integrity rules are not passed onto the new tables; only the column datatype definitions remain. You will need to add a PRIMARY KEY constraint to the copy_d_clients table. Name the primary key copy_d_clients_pk . What is the syntax you used to create the PRIMARY KEY constraint to the copy_d_clients.table?

ALTER TABLE copy_d_clients ADD CONSTRAINT copy_d_clients_pk PRIMARY KEY (client_number);

3. Create a FOREIGN KEY constraint in the copy_d_events table. Name the foreign key
copy_d_events_fk. This key references the copy_d_clients table client_number column. What is the syntax you used to create the FOREIGN KEY constraint in the copy_d_events table?

ALTER TABLE  copy_d_events
ADD CONSTRAINT copy_d_eve_client_number_fk FOREIGN KEY (client_number) REFERENCES  copy_d_clients (client_number) ENABLE;

4. Use a SELECT statement to verify the constraint names for each of the tables. Note that the tablenames must be capitalized.
a. The constraint name for the primary key in the copy_d_clients table is PRIMARY .
b. The constraint name for the foreign key in the copy_d_events table is FOREIGN .

5. Drop the PRIMARY KEY constraint on the copy_d_clients table. Explain your results.

ALTER TABLE copy_d_clients DROP CONSTRAINT copy_d_clients_pk;

6. Add the following event to the copy_d_events table. Explain your results. 
7. Create an ALTER TABLE query to disable the primary key in the copy_d_clients table. Then add the values from #6 to the copy_d_events table. Explain your results.

INSERT INTO copy_d_events (client_number, event_date, event_details) VALUES (12345, TO_DATE('2024-11-22', 'YYYY-MM-DD'), 'Event 2');
8. Repeat question 6: Insert the new values in the copy_d_events table. Explain your results.

ALTER TABLE copy_d_clients ENABLE CONSTRAINT copy_d_clients_pk;

9. Enable the primary-key constraint in the copy_d_clients table. Explain your results.

ALTER TABLE copy_d_events ENABLE CONSTRAINT copy_d_events_fk;

10. If you wanted to enable the foreign-key column and reestablish the referential integrity between these two tables, what must be done?

ALTER TABLE copy_d_events ENABLE CONSTRAINT copy_d_events_fk;

11. Why might you want to disable and then re-enable a constraint?
-- ensure up to date and address potential issues

12. Query the data dictionary for some of the constraints that you have created. How does the data dictionary identify each constraint type?
-- c = check constraint
-- p = primary key constraint
-- u = unique key constraint

Database Programming with SQL
15-1: Creating Views
Practice Activities
Objectives
• List three uses for views from the standpoint of a database administrator
• Explain, from a business perspective, why it is important to be able to create and use logical
subsets of data derived from one or more tables
• Create a view with and without column aliases in the subquery using a single base table
• Create a complex view that contains group functions to display values from two tables
• Retrieve data from a view

Vocabulary
Identify the vocabulary word for each definition below.

-	A subset of data from one or more tables that is generated from a query and stored as a virtual table
--view
-	Name of view
-- view name
-	Creates a view regardless of whether or not the base tables exist
-- create view
-	Derives data from a table, no functions or groups, performs DML operations through the view
-- simple view
-	Creates the view only if the base table exists
-- create view
-	Statement used to create a new view
--create view
-	Specifies a name for each expression selected by the view’s query
--column alias
-	A complete SELECT statement
--view query
-	Derives data from more than one table, contains functions or groups of data, and does not always allow DML operations through the view
--complex view
-	Re-creates the view if it already exists
--create view

Try It / Solve It
1. What are three uses for a view from a DBA’s perspective?
-- restrictions;  decrease complexity; customization/personalization 

2. Create a simple view called view_d_songs that contains the ID, title, and artist from the DJs on Demand table for each “New Age” type code. In the subquery, use the alias “Song Title” for the title column.

SELECT d_songs.id, d_songs.title "Song Title", d_songs.artist
from d_songs INNER JOIN d_types ON d_songs.type_code = d_types.code
where d_types.description = 'New Age'


3. SELECT *
FROM view_d_songs.
What was returned?
-- id, song title, artist

4. REPLACE view_d_songs. Add type_code to the column list. Use aliases for all columns.

CREATE OR REPLACE VIEW view_d_songs AS
SELECT d_songs.id, d_songs.title "Song Title", d_songs.artist, d_songs.type_code
from d_songs INNER JOIN d_types ON d_songs.type_code = d_types.code
where d_types.description = 'New Age'
;


5. Jason Tsang, the disk jockey for DJs on Demand, needs a list of the past events and those
planned for the coming months so he can make arrangements for each event’s equipment setup. As the company manager, you do not want him to have access to the price that clients paid for their events. Create a view for Jason to use that displays the name of the event, the event date, and the theme description. Use aliases for each column name.

CREATE OR REPLACE VIEW jason_event_view AS SELECT event_name AS "Event Name", event_date AS "Event Date", theme_description AS "Theme" FROM events;

6. It is company policy that only upper-level management be allowed access to individual employee salaries. The department managers, however, need to know the minimum, maximum, and average salaries, grouped by department. Use the Oracle database to prepare a view that
displays the needed information for department managers.

CREATE OR REPLACE VIEW dept_salary_stats AS SELECT department_id AS "Department ID", MIN(salary) AS "Minimum Salary", MAX(salary) AS "Maximum Salary", AVG(salary) AS "Average Salary" FROM employees GROUP BY department_id;

Database Programming with SQL
15-2: DML Operations and Views
Practice Activities
Objectives
• Write and execute a query that performs DML operations on a simple view
• Name the conditions that restrict modifying a view using DML operations
• Write and execute a query using the WITH CHECK OPTION clause
• Explain the use of WITH CHECK OPTION as it applies to integrity constraints and data validation
• Apply the WITH READ ONLY option to a view to restrict DML operations

Vocabulary
Identify the vocabulary word for each definition below.
- A pseudocolumn which assigns a sequential value starting with 1
to each of the rows returned from the subquery
= rownum
- Specifies that INSERTS and UPDATES performed through the
view can’t create rows which the view cannot select
= with check option
- xEnsures that no DML operations can be performed on this view
= with read only

Try It / Solve It
Use the DESCRIBE statement to verify that you have tables named copy_d_songs, copy_d_events, copy_d_cds, and copy_d_clients in your schema. If you don't, write a query to create a copy of each.
1. Query the data dictionary USER_UPDATABLE_COLUMNS to make sure the columns in the base tables will allow UPDATE, INSERT, or DELETE. Use a SELECT statement. All table names in the data dictionary are stored in uppercase.

SELECT TABLE_NAME, COLUMN_NAME, UPDATABLE FROM USER_UPDATABLE_COLUMNS WHERE UPDATABLE = 'YES';

2. Use the CREATE or REPLACE option to create a view of all the columns in the copy_d_songs table called view_copy_d_songs.

CREATE OR REPLACE VIEW view_copy_d_songs AS SELECT * FROM copy_d_songs;

3. Use view_copy_d_songs to INSERT the following data into the underlying copy_d_songs table. Execute a SELECT * from copy_d_songs to verify your DML command. See the graphic.

INSERT INTO view_copy_d_songs(id, title, duration, artist, type_code)
VALUES(88, 'Mello Jello', '2 min', 'The What', 4);

4. Create a view based on the DJs on Demand COPY_D_CDS table. Name the view
read_copy_d_cds. Select all columns to be included in the view. Add a WHERE clause to restrict
the year to 2000. Add the WITH READ ONLY option.

CREATE OR REPLACE VIEW read_copy_d_cds  AS
SELECT *
FROM copy_d_cds
WHERE year = '2000'
WITH READ ONLY ;

5. Using the read_copy_d_cds view, execute a DELETE FROM read_copy_d_cds WHERE
cd_number = 90;

DELETE

6. Use REPLACE to modify read_copy_d_cds. Replace the READ ONLY option with WITH CHECK OPTION CONSTRAINT ck_read_copy_d_cds. Execute a SELECT * statement to verify that the view exists.

CREATE OR REPLACE VIEW read_copy_d_cds  AS
SELECT *
FROM copy_d_cds
WHERE year = '2000'
WITH CHECK OPTION CONSTRAINT ck_read_copy_d_cds;

7. Use the read_copy_d_cds view to delete any CD of year 2000 from the underlying copy_d_cds.

DELETE FROM read_copy_d_cds
WHERE year = '2000';

8. Use the read_copy_d_cds view to delete cd_number 90 from the underlying copy_d_cds table.

DELETE FROM read_copy_d_cds
WHERE cd_number = 90;

9. Use the read_copy_d_cds view to delete year 2001 records.

DELETE FROM read_copy_d_cds WHERE year = 2001;

10. Execute a SELECT * statement for the base table copy_d_cds. What rows were deleted?
The row that was deleted
11. What are the restrictions on modifying data through a view?
--delete not possible on multi tables; cannot delete row if more than one base table is addressed

12. What is Moore’s Law? Do you consider that it will continue to apply indefinitely? Support your opinion with research from the internet.
-- Moore’s Law notes that the number of transistors on a microchip will double every 2 years, which notes that computing power will increase as time progresses. 

 

13. What is the “singularity” in terms of computing?
-- potential future that notes that computer intelligence can advance past human intelligence

Database Programming with SQL
15-3: Managing Views
Practice Activities
Objectives
• Create and execute a query that removes a view
• Create and execute a query using an inline view
• Create and execute a top-n-analysis query

Vocabulary

Identify the vocabulary word for each definition below.

-	Asks for the N largest or smallest values in a column
top n 
-	Removes a view
drop view
-	Subquery with an alias that can be used within a SQL statement
inline view
![Uploading image.png…]()
