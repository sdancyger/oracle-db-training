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
• Select and apply character-manipulation functions CONCAT, SUBSTR, LENGTH, INSTR,
LPAD, RPAD, TRIM, and REPLACE in a SQL query.
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
 