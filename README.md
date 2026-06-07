# Database_Project
# Library Management System

## Overview
The Library Management System is a MySQL database project designed to manage books, authors, categories, members, book issues, and reservations in a library. It helps librarians keep track of available books, issued books, and member activities efficiently.

## Features

- Manage books and book categories
- Store author information
- Register library members
- Issue and return books
- Reserve books for members
- Track available book copies
- Calculate and store fines
- Database views for quick reporting

## Database Structure

### Tables

#### 1. Authors
Stores information about book authors.

| Column | Description |
|----------|-------------|
| author_id | Unique author ID |
| author_name | Author name |

#### 2. Categories
Stores book categories.

| Column | Description |
|----------|-------------|
| category_id | Unique category ID |
| category_name | Category name |

#### 3. Books
Stores book information.

| Column | Description |
|----------|-------------|
| book_id | Unique book ID |
| title | Book title |
| author_id | Author reference |
| category_id | Category reference |
| isbn | ISBN number |
| total_copies | Total copies available |
| available_copies | Available copies |
| published_year | Publication year |

#### 4. Members
Stores library member details.

| Column | Description |
|----------|-------------|
| member_id | Unique member ID |
| full_name | Member name |
| email | Email address |
| phone | Contact number |
| address | Member address |
| membership_date | Registration date |
| status | Membership status |

#### 5. Book_Issue
Stores issued book records.

| Column | Description |
|----------|-------------|
| issue_id | Unique issue ID |
| member_id | Member reference |
| book_id | Book reference |
| issue_date | Book issue date |
| due_date | Return due date |
| return_date | Actual return date |
| fine_amount | Fine amount |

#### 6. Reservations
Stores book reservation records.

| Column | Description |
|----------|-------------|
| reservation_id | Unique reservation ID |
| member_id | Member reference |
| book_id | Book reference |
| reservation_date | Reservation date |
| status | Reservation status |

---

## Database Relationships

- One Author can write many Books.
- One Category can contain many Books.
- One Member can issue multiple Books.
- One Member can reserve multiple Books.
- Books are linked with Authors and Categories using Foreign Keys.

---

## Views

### 1. book_availability
Displays book availability status.

**Output:**
- Book ID
- Title
- Available Copies
- Status (Available / Not Available)

### 2. issued_books_details
Displays detailed information about issued books.

**Output:**
- Issue ID
- Member Name
- Book Title
- Issue Date
- Due Date
- Return Date
- Fine Amount

---

## Sample Data Included

The database contains sample records for:

- Authors
- Categories
- Books
- Members
- Issued Books
- Reservations

---

## Technologies Used

- MySQL 8.0
- SQL (DDL, DML, Views, Constraints)
- Relational Database Management System (RDBMS)

---

## Installation

1. Open MySQL Workbench.
2. Create a new database.

```sql
CREATE DATABASE librarymanagementsystem;
USE librarymanagementsystem;
```

3. Import the provided SQL dump file:

```sql
SOURCE Dump20260607.sql;
```

Or use MySQL Workbench:

- Server → Data Import
- Select `Dump20260607.sql`
- Start Import

---

## Learning Concepts Covered

- Database Design
- Primary Keys
- Foreign Keys
- Relationships
- Constraints
- SQL Queries
- Views
- Data Management
- Library Record Tracking

---

## Future Enhancements

- Stored Procedures
- Triggers for automatic fine calculation
- User Authentication
- Librarian Dashboard
- Book Search Functionality
- Report Generation

---

## Author

Developed as a Database Management System (DBMS) project for learning relational database concepts and SQL operations.
