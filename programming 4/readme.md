# Oracle Programming 4

Database Programming: Section 4

• 4-1 Case and Character Manipulation
• 4-2 Number Functions
• 4-3 Date Functions


## Database Programming with SQL
## 4-1: Case and Character Manipulation

### Practice Activities

### Objectives
    • Select and apply single-row functions that perform case conversion and/or character
    manipulation.

    • Select and apply character case-manipulation functions LOWER, UPPER, and INITCAP in a SQL query.
    
    • Select and apply character-manipulation functions CONCAT, SUBSTR, LENGTH, INSTR, LPAD, RPAD, TRIM, and REPLACE in a SQL query.

    • Write flexible queries using substitution variables.

## Vocabulary
### *Identify the vocabulary word for each definition below:*

Dummy table used to view results from functions and calculations
    
    -dual

The arrangement of data for storage or display.
    
    -format

Converts alpha character values to uppercase for the first letter of each word, all other letters in lowercase.
    
    -inticap

Functions that accept character data as input and can return both character and numeric values.
    
    -character manipulation

Removes all specified characters from either the beginning or the ending of a string.
    
    -trim

A symbol that represents a quantity or a relationship between quantities
    
    -operator

Functions that operate on single rows only and return one result per row
    
    -single row

Converts alpha characters to upper case
    
    -upper

Raw data entered into the computer
    
    -input

Concatenates the first character value to the second character value; equivalent to concatenation operator (||).
    
    -concat

Data that is processed into information
    
    -output

Converts alpha character values to lowercase.
    
    -lower

Pads the left side of a character, resulting in a right-justified value
    
    -lpad

Returns specific characters from character value starting at a specific character position and going specified character positions long
    
    -substr

Replaces a sequence of characters in a string with another set of characters.
    
    -replace

Returns the numeric position of a named string.
    
    -instr

Returns the number of characters in the expression
    
    -length

Pads the right-hand side of a character, resulting in a left- justified value.
    
    -rpad

 
 ## Try It / Solve It
 
 1. 
 
 Using the three separate words “Oracle,” “Internet,” and
 “Academy,” use one command to produce the following output:
 
 The Best Class
 Oracle Internet Academy
 
 
 SELECT CONCAT('Oracle', CONCAT(' Internet', ' Academy')) AS "The Best Class"
 FROM DUAL;
 
 2. 
 
 Use the string “Oracle Internet Academy” to produce the following output:
 
 The Net
 net
 
 
 SELECT SUBSTR('Oracle Internet Academy', INSTR('Oracle Internet Academy', 'net'), 3) AS "The Net"
 FROM DUAL;
 
 3. 
 
 What is the length of the string “Oracle Internet Academy”?
 22
 SELECT LENGTH('Oracle Internet Academy') AS "String Length"
 FROM DUAL;
 
 4. 
 
 What’s the position of “I” in “Oracle Internet Academy”?
 
 8
 SELECT INSTR('Oracle Internet Academy', 'I') AS "Position of I"
 FROM DUAL;
 
 5. 
 
 Starting with the string “Oracle Internet Academy”, pad the string to
 create ****Oracle****Internet****Academy****
 
 SELECT LPAD('Oracle', 10, '*') || '****' || LPAD('Internet', 10, '*') || '****' || LPAD('Academy', 10, '*') AS "Padded String" FROM DUAL;
 
 6. 
 
 Starting with the string “Oracle Internet Academy”, pad the string to produce:
 Oracle$$$Internet$$$Academy
 
 SELECT 'Oracle' || '$$$' || 'Internet' || '$$$' || 'Academy' AS "Padded String" FROM DUAL;
 
 7. 
 
 Using the string ‘Oracle Internet Academy’, produce the output shown using the REPLACE
 function.
 
 The Best Class
 Oracle 2013-2014 Academy
 
 SELECT REPLACE(‘Oracle Internet Academy’, ‘Internet’, ‘2013-2014’) AS “The Best Class” FROM dual;
 
 8. 
 
 List the order date and the order total from the Global Fast Foods F_ORDERS table. Name the order total as TOTAL, and fill in the empty spaces to the left of the order total with $.
 
 SELECT ORDER_DATE, LPAD(ORDER_TOTAL, 10, '$') AS TOTAL FROM F_ORDERS;
 
 9. 
 
 Write a query that will output a column called “ADDRESS” which has the following information:
 ZOE TWEE 1009 OLIVER AVENUE BOSTON, MA 12889. Use the Global Fast Foods
 F_CUSTOMERS table.
 
 SELECT 'ZOE TWEE 1009 OLIVER AVENUE BOSTON, MA 12889' AS "ADDRESS"
 FROM DUAL;
 
 10. 
 
 Write a query to return the first character of the first name concatenated to the last_name, the salary, and the department id for employees working in department 20. Give the first expression an alias of Name. Use the EMPLOYEES table. Change the query to use a substitution variable instead of the hard coded value 20 for department id. Run the query for department 30 and 50 without changing the original where-clause in your statement.
 
 SELECT SUBSTR(first_name, 1, 1) || last_name AS “Name”, salary, department_id FROM employees
 
 11. 
 
 Using a substitution variable for the department name, write a query listing department id, department name, and location id for departments located in the_department_of_your_choice. Use the DEPARTMENTS table. Note: All substitution variables in OAE are treated as character strings, so no quotes (‘ ‘) are needed.
 
 SELECT department_id, department_name, location_id 
 FROM departments
 WHERE department_name = :dept_name;
 
 12. Write a query that returns all the employee data depending on the month of their hire date. Use the EMPLOYEES table. The statement should return the month part of the hiredate which is then compared to an abbreviated month (JAN, FEB, MAR) passed into the query via a substitution variable.
 
 SELECT *
 FROM employees
 WHERE TO_CHAR(hire_date, 'MONTH') = UPPER(&month_name);
 
 ## Database Programming with SQL
 ## 4-2: Number Functions
 ## Practice Activities
 
 ### Objectives
 • Select and apply the single-row number functions ROUND, TRUNC, and MOD in a SQL query
 
 • Distinguish between the results obtained when TRUNC is applied to a numeric value and
 ROUND is applied to a numeric value
 
 • State the implications for business when applying TRUNC and ROUND to numeric values
 
 ## Vocabulary
 ## *Identify the vocabulary word for each definition below:*
 
 Used to terminate the column, expression, or value to a specified number of decimal places
    
    -trunc
 
 These functions accept numeric input and return numeric values.
    
    -number functions
 
 Returns the remainder of a division.
 
    -mod
 
 Rounds the column, expression, or value to a set number of decimal places.
 
    -round
 
 ## Try It / Solve It

 1. 
 
 Display Oracle database employee last_name and salary for employee_ids between 100 and 102. Include a third column that divides each salary by 1.55 and rounds the result to two decimal places.
 
 SELECT last_name, salary, 
 ROUND(salary / 1.55, 2) AS new_salary
 FROM employees
 WHERE employee_id BETWEEN 100 AND 102;
 
 2. 
 
 Display employee last_name and salary for those employees who work in department 80. Give each of them a raise of 5.333% and truncate the result to two decimal places.
 
 SELECT last_name, salary, TRUNC(salary * 1.05333, 2) AS new_salary
 FROM employees
 WHERE department_id = 80;
 
 3. 
 
 Use a MOD number function to determine whether 38873 is an even number or an odd number.
 
 SELECT 
 CASE 
 WHEN MOD(38873, 2) = 0 THEN 'Even'
 ELSE 'Odd'
 END AS number_type;
 
 Odd.
 
 
 ## Database Programming with SQL
 ## 4-3: Date Functions
 ## Practice Activities
 
 ## Objectives
 • Select and apply the single-row functions MONTHS_BETWEEN, ADD_MONTHS, NEXT_DAY,
 LAST_DAY, ROUND, and TRUNC that operate on date data

 • Explain how date functions transform Oracle dates into date data or numeric values

 • Demonstrate proper use of the arithmetic operators with dates

 • Demonstrate the use of SYSDATE and date functions

 • State the implications for world businesses to be able to easily manipulate data stored in date format
 
 ## Vocabulary
 ## *Identify the vocabulary word for each definition below:*
 
 A function that returns the current date and time of the database
 server.
 sysdate
 
 Add calendar months to date
    
    add_months
 
 Last day of the month
    
    last_day
 
 Next day of the date specified
    
    next_day
 
 Number of months between due dates

    months_between
 
 ## Try It / Solve It

 1. 
 For DJs on Demand, display the number of months between the event_date of the Vigil wedding and today’s date. Round to the nearest month.
 
 SELECT ROUND(MONTHS_BETWEEN(SYSDATE, event_date)) AS Months_Between
 FROM dj_list
 WHERE event_name = 'Vigil wedding';
 

 2. Display the days between the start of last summer’s school vacation break and the day school started this year. Assume 30.5 days per month. Name the output “Days.”
 
 SELECT (TO_DATE('2024-09-01', 'YYYY-MM-DD') - TO_DATE('2024-06-15', 'YYYY-MM-DD')) AS Days FROM dual;

 3. Display the days between January 1 and December 31.
 
 SELECT (TO_DATE('2024-12-31', 'YYYY-MM-DD') - TO_DATE('2024-01-01', 'YYYY-MM-DD')) AS Days
 
 4. Using one statement, round today's date to the nearest month and nearest year, and truncate it to the nearest month and nearest year. Use an alias for each column.
 
 SELECT ROUND(SYSDATE, 'MM') AS Rounded_Month, ROUND(SYSDATE, 'YYYY') AS Rounded _Year, TRUNC(SYSDATE, 'MM') AS Truncated_Month, TRUNC(SYSDATE, 'YYYY') AS Truncated _Year
 FROM dual;
 
 5. What is the last day of the month for June 2005? Use an alias for the output.
 
 SELECT  LAST_DAY(TO_DATE('2005-06-01', 'YYYY-MM-DD')) AS Last_Day_of_June_2005
 FROM dual;  
 
 6. Display the number of years between the Global Fast Foods employee Bob Miller’s birthday and today. Round to the nearest year.
 
 SELECT ROUND(MONTHS_BETWEEN(SYSDATE, birthday) / 12) AS Years_Between
 FROM F_EMPLOYEES
 WHERE first_name = 'Bob' AND last_name = 'Miller';
 
 7. Your next appointment with the dentist is six months from today. On what day will you go to the dentist? Name the output, “Appointment.”
 
 SELECT ADD_MONTHS(SYSDATE, 6) AS "Appointment"
 FROM DUAL;
 
 8. The teacher said you have until the last day of this month to turn in your research paper. What day will this be? Name the output, “Deadline.”
 
 SELECT LAST_DAY(SYSDATE) AS "Deadline"
 FROM DUAL;
 
 9. How many months between your birthday this year and January 1 next year?
 
 SELECT MONTHS_BETWEEN('2025-01-01', '2024-07-13') AS Months_Between
 FROM DUAL;
 
 SELECT NEXT_DAY('2024-07-13', 'FRIDAY') AS "First Friday"
 FROM DUAL;
 
 10. What’s the date of the next Friday after your birthday this year? Name the output, “First Friday.”
 
 SELECT NEXT_DAY(TO_DATE('2024-07-13', 'YYYY-MM-DD'), 'FRIDAY') AS "First Friday"
 FROM DUAL;
 
 11. Name a date function that will return a number.
 
Months_Between
 
 12. Name a date function that will return a date.
 
Next_Day
 