# PRACTICE
### Assignments for week 3 are below: 

## DP_1_3_Practice

Vocabulary
Identify the vocabulary word for each definition below: 

    - Display data from two or more related tables
        -join
    - A symbol used to perform an operation on some values.
        -operator
    - An implementation of an attribute or relationship in a table.
        -column
    - The capability in SQL to choose the columns in a table that you want returned from a query.
        -projection
    - A value that is unavailable, unassigned unknown, or inapplicable.
        -null
    - Renames a column heading.
        -alias
    - A mathematical equation.
        -expression
    - The capability in SQL to choose the rows in a table returned from a query.
        -selection
    - Retrieves information from the database
        -query
    - Specifies the columns to be displayed
        -select 
    - Specifies the table containing the column listed in the select clause
        -from
    - An individual SQL command
        -statement
    - Part of a SQL statement
        -clause
    - A combination of the two clauses
        -query

### Try It / Solve It
Now you know the basics of a SELECT statement, It's time to practice what you've learned:* 
1. Write a SQL statement that demonstrates projection

        SELECT fruit_name, color, size

        FROM fruits

2. Write a query that displays the last_name and email addresses for all the people in the DJs on
Demand d_client table. The column headings should appear as “Client” and “Email Address.”

        SELECT last_name as "client" , email addresses as "Email Address"
        
        FROM d_client 

3. The manager of Global Fast Foods decided to give all employees at 5%/hour raise + a $.50
bonus/hour. However, when he looked at the results, he couldn't figure out why the new raises
were not as he predicted. Ms. Doe should have a new salary of $7.59, Mr. Miller's salary should
be $11.00, and Monique Tuttle should be $63.50. He used the following query. What should he
have done?
SELECT last_name, salary *.05 +.50
FROM f_staffs;

    The original salary has to be included with the 5% per hour raise and the $0.50 per hour bonus.

    SELECT last_name, salary *1.05 +.50
    FROM f_staffs;

4. Which of the following would be the easiest way to see all rows in the d_songs table?
a. SELECT id, title, duration, artist, type_code
b. SELECT columns
c. SELECT *
d. SELECT all

    c. SELECT *

5. If tax = 8.5% * car_cost and license = car_cost * .01%, which value will produce the largest car
payment?
a. Payment = (car_cost * 1.25) + 5.00 - (tax) - (license)
b. Payment = car_cost * 1.25 + 5.00 - (tax - license)

    b. Payment = car_cost * 1.25 + 5.00 - (tax - license)

6. In the example below, identify the keywords, the clause(s), and the statement(s):
SELECT employee_id, last_name
FROM employees

keywords = 
        
    SELECT , FROM
    
clauses = 
    
    SELECT employee_id, last_name 
    
    FROM employees

statements = 
    
    SELECT employee_id, last_name 
    
    FROM employees

7. Label each example as SELECTION or PROJECTION.

    a. Please give me Mary Adam's email address.

        - selection

    b. I would like only the manager_id column, and none of the other columns.

        - projection

8. Which of the following statements are true?

    a. null * 25 = 0;

    b. null * 6.00 = 6.00

    c. null * .05 = null

    d. (null + 1.00) + 5.00 = 5.00

        c. null * .05 = null


9. How will the column headings be labeled in the following example?
SELECT bear_id bears, color AS Color, age “age”
FROM animals;

    a. bears, color, age

    b. BEARS, COLOR, AGE

    c. BEARS, COLOR, age

    d. Bears, Color, Age

            c. BEARS, COLOR, age


10. Which of the following words must be in a SELECT statement in order to return all rows?
    a. SELECT only

    b. SELECT and FROM

    c. FROM only

    d. SELECT * only

            d. SELECT * only


    
## DP_2_1_Practice

*Vocabulary*

Identify the vocabulary word for each definition below.

- A command that suppresses duplicates
    - distinct
- Links two columns together to form one character data column
    - concatenation
- A group of character data
    - string
- An SQL plus command that displays the structure of a table
    - describe

### Try It / Solve It

1. The manager of Global Fast Foods would like to send out coupons for the upcoming sale. He wants to send one coupon to each household. Create the SELECT statement that returns the customer last name and a mailing address.

    SELECT first_name, last_name, home_address, zip_code

    FROM customer_list

2. Each statement below has errors. Correct the errors and execute the query in Oracle Application Express.

    a.

    SELECT first name

    FROM f_staffs;

        SELECT first_name
        FROM f_staffs;

    b.
    
    SELECT first_name |" " | last_name AS "DJs on Demand Clients"
    
    FROM d_clients;

        SELECT first_name ||" "|| last_name AS "DJs on Demand Clients"
    
        FROM d_clients;
    c.
    
    SELECT DISCTINCT f_order_lines
    
    FROM quantity;

        SELECT DISTINCT f_order_lines
    
        FROM quantity;

    d.
    
    SELECT order number
    
    FROM f_orders;

        SELECT order_number
    
        FROM f_orders;

3. Sue, Bob, and Monique were the employees of the month. Using the f_staffs table, create a
SELECT statement to display the results as shown in the Super Star chart.

    Super Star

    *** Sue *** Sue ***
    *** Bob *** Bob ***
    *** Monique *** Monique ***

4. Which of the following is TRUE about the following query?

    SELECT first_name, DISTINCT birthdate
    FROM f_staffs;

    a. Only two rows will be returned.

    b. Four rows will be returned.

    c. Only Fred 05-Jan-1988 and Lizzie 10-Nov-1987 will be returned.

    d. No rows will be returned
        
            d. No rows will be returned

5. Global Fast Foods has decided to give all staff members a 5% raise. Prepare a report that presents the output as shown in the chart.

    EMPLOYEE LAST NAME CURRENT SALARY SALARY WITH 5% RAISE

    SELECT employee_last_name AS "employee last name" , current_salary AS "current salary" , *1.05 salary AS "salary with 5% raise"
    
    FROM f_staffs

6. Create a query that will return the structure of the Oracle database EMPLOYEES table. Which columns are marked “nullable”? What does this mean?

    DESCRIBE EMPLOYEES

The columns that are nullable do not need to contain values. 

7. The owners of DJs on Demand would like a report of all items in their D_CDs table with the following column headings: Inventory Item, CD Title, Music Producer, and Year Purchased.
Prepare this report.

SELECT 

inventory_item AS "Inventory Item", 

cd_title AS "CD Title", 

music_producer AS "Music Producer", 

year_purchased AS "Year Purchased"

FROM 

D_CDs;


8. True/False -- The following SELECT statement executes successfully:

SELECT last_name, job_id, salary AS Sal

FROM employees;

    true

9. True/False -- The following SELECT statement executes successfully:

SELECT *

FROM job_grades;

    true

10. There are four coding errors in this statement. Can you identify them?

SELECT employee_id, last_name

sal x 12 ANNUAL SALARY

FROM employees;


    SELECT employee_id, last_name,

    sal * AS 12 ANNUAL SALARY

    FROM employees;

11. In the arithmetic expression salary*12 - 400, which operation will be evaluated first?

        salary*12

12. Which of the following can be used in the SELECT statement to return all columns of data in the Global Fast Foods f_staffs table?

    a. column names

    b. *

    c. DISTINCT id

    d. both a and b

        b. *

13. Using SQL to choose the columns in a table uses which capability?

    a. selection

    b. projection

    c. partitioning

    d. join

            b. projection


14. SELECT last_name AS "Employee". The column heading in the query result will appear as:

    a. EMPLOYEE

    b. employee

    c. Employee

    d. "Employee:

            c. Employee

15. Which expression below will produce the largest value?

a. SELECT salary*6 + 100

b. SELECT salary* (6 + 100)

c. SELECT 6(salary+ 100)

d. SELECT salary+6*100

    b. SELECT salary* (6 + 100)

16. Which statement below will return a list of employees in the following format?
Mr./Ms. Steven King is an employee of our company.

a. 

SELECT "Mr./Ms."||first_name||' '||last_name 'is an employee of our company.' AS
"Employees"

FROM employees;

b. 

SELECT 'Mr./Ms. 'first_name,last_name ||' '||'is an employee of our company.'

FROM employees;

c. 

SELECT 'Mr./Ms. '||first_name||' '||last_name ||' '||'is an employee of our company.' AS
"Employees"

FROM employees ;

d. 

SELECT Mr./Ms. ||first_name||' '||last_name ||' '||"is an employee of our company." AS
"Employees"

FROM employees

    c. 

    ELECT 
    'Mr./Ms. '||first_name||' '||last_name ||' '||'is an employee of our company.' AS
    "Employees"

    FROM 
    employees ;


17. Which is true about SQL statements?

a. SQL statements are case-sensitive

b. SQL clauses should not be written on separate lines.

c. Keywords cannot be abbreviated or split across lines.

d. SQL keywords are typically entered in lowercase; all other words in uppercase.

    c. Keywords cannot be abbreviated or split across lines.

18. Which queries will return three columns each with UPPERCASE column headings?

a. 

SELECT "Department_id", "Last_name", "First_name"

FROM employees;

b. 

SELECT DEPARTMENT_ID, LAST_NAME, FIRST_NAME

FROM employees;

c. 

SELECT department_id, last_name, first_name AS UPPER CASE

FROM employees

d. 

SELECT department_id, last_name, first_name

FROM employees;

    b. 

    SELECT DEPARTMENT_ID, LAST_NAME, FIRST_NAME

    FROM employees;

19. Which statement below will likely fail?

    a. SELCT * FROM employees;

    b. Select * FROM employees;

    c. SELECT * FROM EMPLOYEES;

    d. SelecT* FROM employees;

        a. SELCT * FROM employees;