# Sarah Dancyger- Oracle DB Training
### Below please find the assignments for week 1:

# PRACTICE
## DFo_1_2_Practice
1. ABC School District would like to create a student on-line information and registration system to capture student-related
information. The system needs to be designed as an on-line process to allow all new students to register on-line. It should also
allow existing students to update and review all information. Create a list of important data that would need to be captured and
stored in the student registration database.

*Student Information*
- Student first name
- Student last name
- Student date of birth
- Student gender
- Student ID number
- Student phone number
- Student street address
- Student home address county

*School information*
- Student school district
- Student school county

*Student emergency contact*
- Emergency contact name
- Emergency contact phone number
- Emergency contact relationship to student
- Emergency contact home address
- Emergency contact e-mail address

*Student health records*
- Current medications
- Medical history
- Allergies
- Vaccination records
- Health insurance provider
- Primary physician name
- Primary physician phone number
- Primary physician address

*Student academics*
- Active grade
- Date of enrollment
- Prospective graduation date
- Current GPA
- Active class list
- Completed class list
- Prospective class list
- Reports from teachers

*Online access*
- Student username
- Student password
- "Forgot password" option

2. XYZ community would like to create a library management system. The objective is for the database to handle all transactions for
the library. The database needs to store all the data that is relevant to managing the books, managing customers, and the day-to-
day activities of the library. Create a list of important data that would need to be captured and stored in the library management
database.

*Book information*
- Title
- Author
- ISBN number
- Genre
- Language
- Year of publication
- Location of publication
- Series number
- Edition number
- Quantity of availablity
- Location in library
- Status of book (checked out or available)
- Condition of book (fair, good, new)
- Type of book (e-book, paperback, audiobook)

*Customer information*
- Name of customer
- Date of birth
- Phone number
- Home address
- E-mail address
- Library card number
- First date of membership
- Membership expiration date
- Current books on hold
- Current books checked out
- Current books reserved

*Library computer system*
- Book title
- Customer name 
- Customer library card number
- Date of checkout
- Date of needed return
- Extensions for return
- Fees accumulated

*Library statistics*
- Total inventory
- Quantity of books checked out
- Quantity of books reserved
- Quantity of books returned on time
- Quantity of books returned late
- Quantity of books never returned
- Number of duplicate copies of books
- Quantity of books in fair condition 
- Quantity of books in good condition 
- Quantity of books in new condition 
- Specific genre quantity
- Popularity ratio

## DFo_1_3_Practice

1. Identify the type of database model that has been represented in the given model snapshots:

- a. Hierarchial database model 
    - This is a tree-like model where each node (employee, part-time, full-time, etc.), are connected by links/branches.

- b.  Network database model 
    - Flexible way to represent objects and their relationships, with the records connecting to each other through links. Each record also contains only one value, and each link will connect two records. 

- c. Object-oriented database model
    - Each object has a value set for the object's attributes, as well as the methods that operate on the object's state. 

- d. Flat file database model
    -  Designed around one table, where plain-text is used, and each line has only one record.

- e. Relational database model
    - Organization of data in tables (rows and columns), with each field only being able to contain one value. 

## DFo_1_4_Practice

1. LibBook is a successful digital library that rents CDs and provides access to Internet for browsing their repository of articles and magazines. With the growing business, LibBook needs to enhance their information system to support proposed changes to the business. LibBook attracts new members easily and the number of members is growing rapidly. The membership base is not stable, however, which is a cause for concern. The main idea is to introduce the concept of membership at LibBook. Members will pay a membership fee and initially, there will be three types of membership (corporate, student, individual) although more may be introduced later. Student membership is free. Corporate and Faculty memberships incur a fee but entitle the member to privileges. The type of membership can be changed only if sufficient justification is provided. 
    - Your task is to identify the business rules and the associated constraints from the case scenario described.
        - Business Rules: 
            - Membership assignment is required (corporate, student, individual).
            - More membership options may be available in the future.
            - Depending on the membership, a fee may be required.
            - Corportate and faculty memberships have a fee.
            - Student membership is free.
            - Corporate and faculty memberships provide additional privileges to the customer. 
            - Membership type can only be changed if sufficient justification is provided.
            
        - Associated Constraints: 
            - Customers can only belong to one membership type (corporate, student, or individual).
            - Memberships cannot be changed.
            - Corporate and faculty members need to pay a fee.
            - Student memberships are not receiving the additional privileges that corporate and faculty members receive. 
            - If a member wants to change membership type, justification will be needed and will have to be reviewed. 



2. Star Care hospital is a multi-specialty hospital that caters to needs of different patients. Every doctor registered with this hospital is assigned a unique ID that starts with the letter "DC". The hospital ensures that the doctors associated with them have a minimum of seven years of working experience. Every patient is required to register with the hospital on their first visit. When a patient arrives, a unique patient number starting with the letters "PT" is assigned to him/her. 
    - Your task is to identify the business rules and the associated constraints from the case scenario described.
        - Business Rules: 
            - Every registered doctor has a unique ID.
            - Each uniquie ID begins with "DC."
            - Doctors must have a minimum of seven years working experience.
            - Every patient needs to register with the hospital during the initial visit. 
            - When a patient arrives, patients receive a unique patient number.
            - When a patient arrives, a unique patient number is provided and begins with "PT."

        - Associated Constraints: 
            - Every registered doctor must have the unique ID that begins with "DC."
            - Every patient must have the unique patient number that begins with "PT."
            - Doctors that do not have seven years experience cannot be affliated with the hospital.
            - The current system needs to track all the registered doctors to ensure criteria of seven years experience is met.
            - The current system needs to track all the patients (outpatient, emergency room, admissions).

## DFo_2_1_Practice

*In this practice you analyze the features of multiple table databases from a set of examples.*


1. Identify the possible tables and associated fields from the given scenario:

Book.com is an online virtual store on the Internet where customers can browse the catalog and select products of interest.

    a. Every book has a title, ISBN, year and price. The store also keeps the author and publisher for any book.

        a.  Table = Book
            Fields = title, ISBN, year, price
            Primary key = book_ID

    b. For authors, the database keeps the name, address and the URL of their homepage.

        b.  Table = Authors
            Fields = name, address, homepage_URL
            Primary key = author_ID


    c. For publishers, the database keeps the name, address, phone number and the URL of their website.

        c.  Table = Publishers
            Fields = name, address, phone_number, website_URL
            Primary key = publisher_ID

    d. The store has several warehouses, each of which has a code, address and phone number.

       d.   Table = Warehouse_store
            Fields = code, address, phone_number
            Primary key = warehouse_store_ID

    e. The warehouse stocks several books. A book may be stocked at multiple warehouses.

        e.  Table = Warehouse_stocks
            Fields = stock_quantity

    f. The database records the number of copies of a book stocked at various warehouses.

        f.  Table = Database_stocks
            Fields = stock_quantity

    g. The bookstore keeps the name, address, email-id, and phone number of its customers.
        g.  Table = Customers
            Fields = name, address, email_ID, phone_number
            Primary key = Customer_ID

    h. A customer owns several shopping carts. A shopping cart is identified by a Shopping_Cart_ID and contains several books.

        h.  Table = Shopping_carts
            Fields = cart_quantity
            Primary key = Shopping_cart_ID

    i. Some shopping carts may contain more than one copy of same book. The database records the number of copies of each book in any shopping cart.
        i.  Table = Shopping_carts_content
            Fields = stock_quantity

    j. At that time, more information will be needed to complete the transaction. Usually, the customer will be asked to fill or select a billing address, a shipping address, a shipping option, and payment information such as credit card number. An email notification is sent to the customer as soon as the order is placed.

        j.  Table = Transaction_stage
            Fields = billing_address, shipping_address, shipping_option, payment_type, e-mail_update
 
 
 
2. ABC Ltd plans to computerize its sales ordering and stock control system. A feasibility study has strongly suggested that a relational database system be installed. The details of ABC's sales and stock control are as follows:

    a. Customers send in orders for goods. Each order may contain requests for variable quantities of one or more products from ABC's range. ABC keeps a stock file showing for each product the product details and the preferred supplier, the quantity in stock, the reorder level and other details.

        a.  Table = Customers
            Fields = cart_quantity
            Primary key = Customer_ID

        a.  Table = Products
            Fields = product_name, preferred_supplier, product_stock, product_reorder_level, other_details
            Primary key = Product_ID


    b. ABC delivers those products that it has in stock in response to the customer order and an invoice is produced for the dispatched items. Any items that were not in stock are placed on a back order list and these items are usually re-ordered from the preferred supplier. Occasionally items are ordered from alternative sources.

        b.  Table = Invoice
            Fields = invoice_number, invoice_date, invoice_availablity
            Primary key = Invoice_ID

    c. In response to the invoices that are sent out to ABC's customers, the customers send in payments. Sometimes a payment will be for one invoice, sometimes for part of an invoice and sometimes for several invoices and part-invoices.

        c.  Table = Payments
            Fields = payment_amount, payment_type, payment_date
            Primary key = Payment_ID


    d. Identify the tables and associated fields from the above scenario.



## DFo_2_2_Practice

*In this practice, you will illustrate the difference between an idea and a physical result.*


1. Provide five reasons for creating a conceptual data model.

    - Allows for the identification of relationships among entities.
    - Can capture the functional and informational needs of a business.
    - Can assist with reflecting future needs of a business. 
    - Can assist with addressing what is conceptually ideal for a business without addressing what is possible physically. 
    - Helps document important entities and their relationships. 

2. List two examples of conceptual models and physical models.

    - Conceptual models:
        - Entity-relationship diagram
        - Online shopping application
        - Flow chart

    - Physical models:
        - Hierarchical database model
        - Design for a house


## DFo_2_3_Practice

     Exercise 1: Identify and draw entities as a beginning of an ERD


        In this practice, you identify and add the entities for an Academic Database, or in other words a School Management System. For your convenience, here is a summary of how the Academic Database (School Management System) works:

        a. A School/University has many Departments which offer courses to students in a given academic session.

        b. Each of these courses is taught by a faculty.

        c. Students enroll for different courses in an academic session.
        
        d. Besides the registration details, the parent information of the student also needs to be maintained by the University/School.

        e. The Department maintains the student’s attendance details which would decide the eligibility of the student to take up the exams for that academic session.

        f. For each academic session, exams are conducted and the results are shared with the student within a stipulated period of time.

        g. The Department also maintains a log of the Faculty login and logout time for their reporting needs.
        Tasks
        
            1. With the information provided above, identify and create the entities for the School Management System.
                - school/university
                    - school_ID
                    - school_address
                    - school_name
                - departments
                    - department_ID
                    - department_name
                - enrollment
                    - enrollment_ID
                    - name
                    - faculty_ID
                - courses
                    - course_ID
                    - course_name
                - faculty
                    - faculty_ID
                    - name
                    - faculty_email
                    - faculty_phone
                - students
                    - student_ID
                    - student_name
                    - student_email
                    - student_phone_number
                - registration details
                    - registration_ID
                    - course_ID
                    - semester_ID
                    - month
                    - year
                - attendance of students
                    - attendance_ID
                    - student_ID
                - exams
                    - exam_ID
                    - student_ID
                    - course_ID
                    - exam_score
                    - exam_class
                - faculty login time
                    - factulty_ID
                    - login_time
                - faculty logout time
                    - faculty_ID
                    - logout_time
    
    Exercise 2: Identify and add Attributes and corresponding Mandatory and Optional notation to ERD.
    
    *In this practice, you identify the attributes and their associated optionality notation in the entities which you have created in Exercise 1.*
    
            1. Add the appropriate attributes as well as the optionality (*, °) to all the entities of the Academic Database.

            - school/university
                    - school_ID             * Required
                    - school_name           * Required
                    - school_address        ° Optional
                    - school_county         ° Optional
                - departments
                    - department_ID         * Required
                    - department_name       * Required
                - enrollment
                    - enrollment_ID         * Required
                    - name                  * Required
                    - faculty_ID            * Required
                - courses
                    - course_ID             * Required
                    - course_name           * Required
                - faculty
                    - faculty_ID            * Required
                    - name                  * Required
                    - faculty_email         * Required
                    - faculty_phone         ° Optional
                - students
                    - student_ID            * Required
                    - student_name          * Required
                    - student_email         * Required
                    - student_phone_number  ° Optional
                - registration details
                    - registration_ID       * Required
                    - course_ID             * Required
                    - semester_ID           * Required
                    - month                 * Required
                    - year                  * Required
                - attendance of students
                    - attendance_ID         * Required
                    - student_ID            * Required
                - exams 
                    - exam_ID               * Required
                    - student_ID            * Required
                    - course_ID             * Required
                    - exam_score            * Required
                    - exam_class            * Required
                - faculty login time
                    - factulty_ID           * Required
                    - login_time            * Required
                    - department_name           ° Optional
                - faculty logout time
                    - faculty_ID            * Required
                    - logout_time           * Required
                    - department_name            ° Optional


    ## DFo_2_4_Practice

Exercise 1: Identify the Unique Identifier and corresponding Primary keys


*In this practice you identify the unique identifiers and the corresponding primary keys from the given scenarios.*

            
    1. How do you find a particular song in the whole collection? What would be a unique identifier for SONG?
        - In order to find a particular song in the whole collection, "song_ID" as the unique identifier would have to be used. 

    2. Think about all the students in the classroom. Each student is described by several traits or attributes. Which attribute or attributes allow you to pick a single student from the rest of the class?
        - Attributes that would allow me to pick a single student from the rest of the class would include:
            - student_ID
            - student_name
            - semester
            - class_section

    3. For each entity, select the attribute that could be the unique identifier of each entity.

        - Entity: STUDENT
        - Attributes: student ID, first name, last name, address
                --> student_ID

        - Entity: MOVIE
        - Attributes: title, date released, producer, director
                --> title

        - Entity: LOCKER
        - Attributes: size, location, number
                --> number




Exercise 2: Identify the Unique Identifiers and add to the ERD

*In this practice, you will identify unique identifiers and add to an ERD.*

1. Use the Academic Database ERD from the previous exercises to identify the following:

    a. Unique Identifiers
        - school_ID
        - department_ID
        - enrollment_ID
        - faculty_ID
        - course_ID
        - attendance_ID
        - semester_ID

    b. Candidate Unique Identifiers
        - student_email
        - faculty_email
        - student_phone_number
        - faculty_phone_number
        - department_name
        - course_name
        - name
        - month
        - year
        - exam_score
        - exam_class
        - department_name
        - login_time
        - logout_time


## DFo_2_5_Practice


Exercise 1: Identify relationships from the ERD

*In this practice, you identify the relationships from the ERD diagrams and write the ERDish sentences.*


1. Read the relationship. Which text corresponds to the diagram?

a. 

    - Each EMPLOYEE may be assigned to one or more DEPARTMENTs.
    - Each DEPARTMENT must be responsible for one or more EMPLOYEEs.

b. 

    - Each EMPLOYEE must be assigned to one and only one DEPARTMENT.
    - Each DEPARTMENT must be responsible for one or more EMPLOYEEs.

c. 

    - Each EMPLOYEE must be assigned to exactly one DEPARTMENT.
    - Each DEPARTMENT may be responsible for exactly one EMPLOYEE


The answer is "b" because the diagram displays that multiple employees can be assignmeed to one department / one department is responsible for multiple employees.


2. Read each relationship in the model below. For each relationship, write the ERD statement and your comments. Use your
knowledge of normal people and towns in your comments.

- A person is born in a town.
- A town can be the birthplace of a person.
- A person can live in a town.
- A town can be the hometown to multiple people.
- A person can visit a town. 
- Towns can be visited by people. 
- One person is the mayor of a town. 
- A town can be governed by one person. 


Exercise 2: Analyze and Model Relationships


*In this practice, you analyze and model the relationships for the following entities, which you created in the Academic Database previously.*


    1. Write the ERDish for each of the relationships in the Academic Database including relationship names, optionality and cardinality.
    
    Draw the ERD including the relationships

- Each course has one department
    - cardinality- one and only one
    - optionality - mandatory
- Each course has an academic session
    - cardinality- one and only one
    - optionality - mandatory
- Each course has students 
    - cardinality- one or more
    - optionality - mandatory
- Each course has exams
    - cardinality- one or more
    - optionality - mandatory
- Each faculty has one academic session
    - cardinality - one and only one
    - optionality - mandatory
- Each faculty has one or more courses
    - cardinality- one or more
    - optionality - mandatory
- Each faculty has a department
    - cardinality- one or more
    - optionality - mandatory
- Each faculty has students
    - cardinality- one or more
    - optionality - mandatory
- Each faculty creates exams
    - cardinality- one or more
    - optionality - mandatory
- Each department has an academic session
    - cardinality- one or more
    - optionality - mandatory
- Each department has faculty
    - cardinality- one or more
    - optionality - mandatory
- Each department has courses
    - cardinality- one or more
    - optionality - mandatory
- Each department has parent information
    - cardinality- one or more
    - optionality - mandatory
- Each academic session has faculty
    - cardinality- one or more
    - optionality - mandatory
- Each academic session has faculty
    - cardinality- one or more
    - optionality - mandatory
- Each academic session has courses
    - cardinality- one or more
    - optionality - mandatory
- Each parent information has a student
    - cardinality- one and only one
    - optionality - mandatory
- Each parent information is stored within the department
    - cardinality- one and only one
    - optionality - mandatory
- Each student has courses
    - cardinality- one or more
    - optionality - mandatory
- Each student has exams.
    - cardinality- one or more
    - optionality - mandatory
- Each student has classes within different departments
    - cardinality- one or more
    - optionality - mandatory
- Each student has an academic session
    - cardinality- one and only one
    - optionality - mandatory
- Each student has parent information
    - cardinality- one and only one
    - optionality - mandatory
- Each student is taught by faculty
    - cardinality- one or more
    - optionality - mandatory
- Each exam is taken by students
    - cardinality- one or more
    - optionality - mandatory
- Each exam is provided within different courses
    - cardinality- one or more
    - optionality - mandatory
- Each exam is within an academic session
    - cardinality- one and only one
    - optionality - mandatory
- Each exam is provided under a department
    - cardinality- one and only one
    - optionality - mandatory
- Each exam is administered by faculty
    - cardinality- one or more
    - optionality - mandatory


## DFo_2_6_Practice

Exercise 1: Identify the components in the ERD

*In this practice you will identify the components in a given simple ERD.*

1. Identify the possible Entities and Attributes from the given scenario.

A company has several departments. Each department has a supervisor and at least one employee. Employees must be assigned to at least one, but possibly more departments. At least one employee is assigned to a project, but an employee may be on vacation and not assigned to any projects. The important data fields are the names of the departments, projects, supervisors and employees, as well as the supervisor and employee number and a unique project number.

- Entities:
    - departments
    - supervisor
    - employees
    - projects
- Attributes: 
    - department_name
    - department_ID
    - supervisor_name
    - supervisor_ID
    - employee_name
    - employee_ID
    - project_name
    - project_ID

- One company has several departments
    - cardinality = one or more
- Each department has one supervisor
    - cardinality = one and only one
- Each department has at least one employee
    - cardinality = one or more
- At least one employee is assigned to one project.\
    - cardinality = one or more
- An employee may not be assigned to a project if on vacation. 

2. Read the given business scenario. Draw the entities HAIRSTYLIST and CLIENT. List the attributes associated with each entity and specify whether they are mandatory or optional. Identify the UIDs. Follow the diagramming conventions discussed. State the ERDish for the relationships.

“In our salon, we have a number of hairstylists. They are all salaried employees, so we keep a record of their first name, last name, address, phone number, social-security number, and salary. During the course of a day, a hairstylist may see several clients. On a slow day, a hairstylist may not work on anyone at all. We have several walk-in clients, and they each get assigned to one hairstylist. We just ask for their first name. We also have customers who call to make an appointment. When they do this, we ask for their first name, last name, and phone number. We also ask if they would like a specific hairstylist. If they have no preference, we assign one for them. Of course, they are allowed to switch to another hairstylist for their next visit to the salon. We are interested in tracking the daily appointments -- which stylist works on which client during a given day.”

- Entities:
    - Hairstylist
    - Client

- Attributes:  
    - Hairstylist
        - hairstylist_first_name
        - hairstylist_last_name
        - hairstylist_address
        - hairstylist_phone_number
        - hairstylist_social_security_number
        - hairstylist_salary
        - hairstylist_daily_client_quantity

    - Client
        - client_first_name
        - client_last_name
        - client_phone_number
        - client_specific_hairstylist

- One hairstylist can have multiple clients
    - cardinality = one or more
- One hairstylist can have one salary
    - cardinality = one and only one
- One client can have one hairstylist per visit
    - cardinality = one or more
- One client can have multiple appointments
    - cardinality = one or more


3. Read the given business scenario. Draw the entities  TEACHER and COURSE and CLASS. List the attributes underneath each
entity. Specify whether they are mandatory or optional. Identify the UIDs. . State the ERDish for the relationships.

“We have several teachers at our school. A teacher can be assigned up to three classes per semester. If a teacher is on sabbatical, he doesn’t teach that semester. We keep a record of the teacher’s first name, last name, address, phone number, and email address. Our school offers many courses -- such as Data Modeling, Introduction to SQL, Trigonometry Physics, and Biology. Each course has a code. For example: Data Modeling would be DM001, Trigonometry would be TR004, etc. During each semester, a course may be taught in several classes -- so there could be two classes of Physics, three classes of Biology, etc. Each class can be taught by only one teacher. We assign a unique ID for each class, and we also keep track of the day it is taught, the time, and the
classroom.”

- Entities:
    - Teachers
    - Course
    - Class

- Attributes:
    - teacher_first_name
    - teacher_last_name
    - teacher_address
    - teacher_phone_number
    - teacher_email
    - teacher_ID
    - course_type
    - course_name
    - course_code
    - course_ID
    - class_quantity
    - class_ID

- One teacher can be assigned to up to three classes
    - cardinality = one to many
- One class can be taught by one teacher
    - cardinality = one and only one 
- One course can be taught in several classes
    - cardinality = one to many


## DFo_3_1_Practice

Exercise 1: Resolve M:M Relationships

*In this practice, you will resolve the following M: M relationships within the Academic database. Add additional attributes in the
intersection entities where needed.*

1. Resolve M: M relationships between STUDENT and the COURSE using a barred relationship
- Entities: 
    - Student
    - Course

- Attributes: 
    - first_name
    - last_name
    - student_ID_number
    - ID_name
    - registration_year
    - email
    - number_of_working_days
    - number_of_days_off
    - exam_eligibility
    - course_ID
    - course_name
    

-Students enroll in courses.


2. Resolve M: M relationships between FACULTY and the COURSE.
- Entities: 
    - Faculty
    - Course
- Attributes: 
    - first_name
    - last_name
    - email
    - login_date
    - login_time
    - details
    - faculty_ID_number
    - course_ID
    - course_name


-Faculty teach courses.

-Courses are taught by multiple faculty.


3. Resolve M: M relationships between STUDENT,COURSE and EXAM
- Entities:
    - Course
    - Student
    - Exam

- Attributes:
    - exam_ID
    - exam_name
    - exam_type
    - exam_start_date
    - exam_description
    - first_name
    - last_name
    - email
    - login_date
    - login_time
    - details
    - faculty_ID_number
    - course_ID
    - course_name
    - student_ID_number
    - ID_name
    - registration_year
    - number_of_working_days
    - number_of_days_off
    - exam_eligibility

-Students take exams in courses

-Exams are provided to students during courses

-Exams are taken by students who are enrolled in courses

-Students enroll in courses to take exams

-Courses have students that take exams


Exercise 2: Adding nontransferability option to an ERD


*In this practice, you create the ERD from the given scenario and add nontransferability option to it.*


1. A STUDENT will be assigned an EXAM RESULT after taking an exam. Once an EXAM RESULT has been issued, it cannot be transferred to another STUDENT.

- Entities:
    - Student
    - Exam
- Attributes:
    - first_name
    - last_name
    - student_ID
    - exam_eligibility
    - exam_type
    - exam_result

-One student can receive only one exam result. 

-One exam result can be provided to only one student, and cannot be transferred to another student.


## DFo_3_2_Practice

Exercise 1: Track Data Change over Time

*In this practice you use scenarios to identify data that changes over time and construct ERD models that incorporate the element of data over time.*


1. Construct the ERD for the given scenario.

In the Academic Database a Grade is issued to each STUDENT for each COURSE taken and stored in the STUDENT COURSE
DETAIL entity. A STUDENT may decide to re-take a COURSE to better their Grade. The administration would like to keep a record of the old/previous Grade as well as the new Grade. Show how the ERD would be modified to include historical Grades if the STUDENT should have them. ** We will not make this actual change to the ERD.
- Entities:
    - Student
    - Course
    - Student_course_detail
- Attributes:
    - student_ID
    - course_ID
    - course_detail_result
    - grade_result

-A student receives a grade for each course.

-A student's grade is stored in the student_course_detail.

-A course can be re-taken if a student decides to improve a grade.



2. Examine the ERD that represents classroom assignments for different exams.



a. Why is start time part of the UID of ASSIGNMENT?
- "Start time" is part of the unique ID of the ASSIGNMENT entity due to it's specificity when relating to a student. All students begin exams at different start times, which is a unique distinction between different students. 

b. Name at least three time-related constraints. For example: End time must be later than start time. Indicate if the constraint represents conditional non-transferability
- Exams must begin at designated start time
- Exams must start on the date of the exam
- Exams must start at the start time and end at the end time
- Exams must be completed within start and end time frame


## DFo_3_3_Practice

Exercise 1: Relational Databases

*In this practice you will analyze the given table structure and bring the table to the specified normal form.*

1. Analyze the given table which is not normalized. The table holds information specific to items such as the Item ID, Color of the item, and the Unit price of each of the item. Some of the rows in the table have repeating group of information. 

Evaluate the data in the table and bring the table to first normal form:

- 1NF = A single value ; no mult-valued attributes present.
- The column for colors should have only one color and not two separated by a comma.

2. Analyze the given table. The table is in the first normal form and has composite primary key made up of the Suppler ID and Store Id. The non-key attribute location is only dependent on the Store ID.

Evaluate the data stored in the table and bring the table to second normal form:

- 2NF = Any non-unique ID attribue is dependent on the entire unique ID. 1NF must be achieved prior. 
- Store ID and Location
- Store ID and supplies ID

3. Analyze the given table and the data stored. In the table the Book ID is the primary key and the Category Description is dependent on the Category ID. 

Evaluate the data stored in the table and eliminate the transitive dependency to bring the table to the third normal form:

- 3NF = No non-unique ID attribute can be dependent on another non unique ID attribute. 2NF much be achieved prior. 


Exercise 2: Normalize Academic Database ERD

*In this practice, you use un-normalized database models to create normalized database models.*

1. For the Academic Database ERD, evaluate each entity against the rules of normalization, identify the misplaced attributes, and explain which rule of normalization each misplaced attribute violates.
- Entities:
    - Parent_information
    - Student_course_detail
    - Student
    - Academic_session
    - Department
    - Course
    - Exam_result
    - Exam
    - Online
    - Seated
    - Faculty_course_detail
    - Faculty
- Attributes:
    - grade
    - exam_ID
    - exam_start_time
    - exam_name
    - exam_description
    - course_ID
    - course_name
    - student_first_name
    - student_last_name
    - registration_year
    - email
    - number_of_working_days
    - number_of_days_off
    - exam_eligibility
    - department_ID
    - department_name
    - department_head
    - faculty_ID
    - faculty_first_name
    - faculty_last_name
    - faculty_email
    - login_date
    - login_time
    - details
    - logon_ID
    - logon_password
    - building
    - room
    - date_time
    - contact_hours


Exercise 3: Validate an ERD for Normalization

1. Evaluate the following unnormalized data in the USER entity and develop an entity relationship diagram that is normalized to third normal form.
- ff

2. A color scheme for a car includes specifications for paint color for the body and the interior colors and materials. For example: The “Desert” color scheme includes silver paint and gray leather interior; the “Sunburst” color scheme includes gold paint and cream leather interior. Does the model below follow the rules of Third Normal Form? If you spot a violation, correct it.
- dd


Exercise 4: Gather database requirements and Business Rules

*In this practice you will analyze the case scenario provided and identify business rules.*

1. Book.com is an online store on the Internet where customers can browse the catalog and select products of interest.
    
        a. Every book has a title, isbn, year and price. The store also keeps the author and publisher for any book.
        
        b. For authors, the database keeps the name, address and the url of their homepage.

        c. For publishers, the database keeps the name, address, phone number and the url of their website.

        d. The store has several warehouses, each of which has a code, address and phone number.
        
        e. The warehouse stocks several books. A book may be stocked at multiple warehouses.
        
        f. The database records the number of copies of a book stocked at various warehouses.

        g. The bookstore keeps the name, address, email-id, and phone number of its customers.
        
        h. A customer owns several shopping carts. A shopping cart is identified by a Shopping_Cart_ID and contains several books.
        
        i. Some shopping carts may contain more than one copy of same book. The database records the number of copies of each book in any shopping cart.
        
        j. At that time, more information will be needed to complete the transaction. Usually, the customer will be asked to fill or select a billing address, a shipping address, a shipping option, and payment information such as credit card number. An email notification is sent to the customer as soon as the order is placed.

    Your task is to identify the business rules.

2. Identify if the given description can be categorized as a Structural Business rule, Procedural Business rule or Programmatic Business rule.
- ff