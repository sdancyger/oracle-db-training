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

Tasks
1. Identify the possible tables and associated fields from the given scenario:
Book.com is an online virtual store on the Internet where customers can browse the catalog and select products of interest.
    a. Every book has a title, ISBN, year and price. The store also keeps the author and publisher for any book.

    b. For authors, the database keeps the name, address and the URL of their homepage.

    c. For publishers, the database keeps the name, address, phone number and the URL of their website.

    d. The store has several warehouses, each of which has a code, address and phone number.

    e. The warehouse stocks several books. A book may be stocked at multiple warehouses.

    f. The database records the number of copies of a book stocked at various warehouses.

    g. The bookstore keeps the name, address, email-id, and phone number of its customers.

    h. A customer owns several shopping carts. A shopping cart is identified by a Shopping_Cart_ID and contains several books.

    i. Some shopping carts may contain more than one copy of same book. The database records the number of copies of each book in any shopping cart.

    j. At that time, more information will be needed to complete the transaction. Usually, the customer will be asked to fill or select a billing address, a shipping address, a shipping option, and payment information such as credit card number. An email notification is sent to the customer as soon as the order is placed.
    
        - Possible tables and associated fields include: 

            a.  Table = Book
                Fields = title, ISBN, year, price
                Primary key = book_ID

            b.  Table = Authors
                Fields = name, address, homepage_URL
                Primary key = author_ID

            c.  Table = Publishers
                Fields = name, address, phone_number, website_URL
                Primary key = publisher_ID

            d.  Table = Warehouse_store
                Fields = code, address, phone_number
                Primary key = warehouse_store_ID

            e.  Table = Warehouse_stocks
                Fields = stock_quantity
                

            f.  Table = Database_stocks
                Fields = stock_quantity

            g.  Table = Customers
                Fields = name, address, email_ID, phone_number
                Primary key = Customer_ID
            
            h.  Table = Shopping_carts
                Fields = cart_quantity
                Primary key = Shopping_cart_ID
                
            i.  Table = Shopping_carts_content
                Fields = stock_quantity
            
            j.  Table = Transaction_stage
                Fields = billing_address, shipping_address, shipping_option, payment_type, e-mail_update

2. ABC Ltd plans to computerize its sales ordering and stock control system. A feasibility study has strongly suggested that a relational database system be installed. The details of ABC's sales and stock control are as follows:
    a. Customers send in orders for goods. Each order may contain requests for variable quantities of one or more products from ABC's range. ABC keeps a stock file showing for each product the product details and the preferred supplier, the quantity in stock, the reorder level and other details.
    b. ABC delivers those products that it has in stock in response to the customer order and an invoice is produced for the dispatched items. Any items that were not in stock are placed on a back order list and these items are usually re-ordered from the preferred supplier. Occasionally items are ordered from alternative sources.
    c. In response to the invoices that are sent out to ABC's customers, the customers send in payments. Sometimes a payment will be for one invoice, sometimes for part of an invoice and sometimes for several invoices and part-invoices.
    d. Identify the tables and associated fields from the above scenario.

