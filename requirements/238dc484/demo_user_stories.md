# User Stories: Library Management System

**Total User Stories:** 11
**Estimated Effort:** 32 days

## Sprint Week 1: User Authentication

### US001: User Registration
The system shall allow new members to register in the library system.

**Acceptance Criteria:**
- New members can register with a unique username and password.
- Registration process includes validation of required fields.
- Registration success message is displayed.

**Linked FRs:** FR1

### US002: User Login
The system shall allow registered users to log in using username and password.

**Acceptance Criteria:**
- Users can log in with their registered username and password.
- Login success message is displayed.
- Invalid login attempts are handled gracefully.

**Linked FRs:** FR2

## Sprint Week 2: Book Management

### US003: Book Management - Add New Books
The librarian shall be able to add new books to the system.

**Acceptance Criteria:**
- Librarian can add a new book with title, author, ISBN, and category.
- Book details are stored in the database.
- Confirmation message is displayed.

**Linked FRs:** FR3

### US004: Book Management - Update Book Details
The librarian shall be able to update book details.

**Acceptance Criteria:**
- Librarian can update existing book details.
- Updated book details are stored in the database.
- Confirmation message is displayed.

**Linked FRs:** FR3

## Sprint Week 3: Search Functionality

### US005: Book Management - Delete Books
The librarian shall be able to delete books from the system.

**Acceptance Criteria:**
- Librarian can delete a book.
- Book details are removed from the database.
- Confirmation message is displayed.

**Linked FRs:** FR3

### US006: Book Management - View Available Books
The librarian shall be able to view available books.

**Acceptance Criteria:**
- Librarian can view a list of available books.
- Book availability status is displayed.
- Confirmation message is displayed.

**Linked FRs:** FR3

### US007: Search Books
The system shall allow users to search books by title, author, ISBN, and category.

**Acceptance Criteria:**
- Users can search for books using title, author, ISBN, or category.
- Search results are displayed.
- Confirmation message is displayed.

**Linked FRs:** FR4

## Sprint Week 4: Borrowing and Fine Management

### US008: Issue Book
The librarian shall be able to issue books to members.

**Acceptance Criteria:**
- Librarian can issue a book to a member.
- Book is marked as issued in the database.
- Confirmation message is displayed.

**Linked FRs:** FR5

### US009: Return Book
The system shall allow members to return borrowed books.

**Acceptance Criteria:**
- Member can return a borrowed book.
- Book is marked as returned in the database.
- Confirmation message is displayed.

**Linked FRs:** FR6

### US010: Fine Calculation
The system shall automatically calculate fines if the book is returned after the due date.

**Acceptance Criteria:**
- Fines are calculated based on the number of days the book is overdue.
- Fines are stored in the database.
- Confirmation message is displayed.

**Linked FRs:** FR7

### US011: View Borrowed Books
Members shall be able to view books currently borrowed.

**Acceptance Criteria:**
- Member can view a list of books currently borrowed.
- Borrowed books are displayed.
- Confirmation message is displayed.

**Linked FRs:** FR8
