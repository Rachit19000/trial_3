# User Stories: Movie Hall Management System

**Total User Stories:** 11
**Estimated Effort:** 28 days

## Sprint Week 1: User Authentication

### US1: User Registration
Allow customers to register using personal details such as name, email, and password.

**Acceptance Criteria:**
- User can provide name, email, and password
- User receives confirmation upon successful registration
- Duplicate emails are not allowed

**Linked FRs:** FR1

### US2: User Login
Allow registered users to log in securely.

**Acceptance Criteria:**
- User can provide login credentials
- User receives confirmation upon successful login
- Incorrect credentials result in failure

**Linked FRs:** FR2

## Sprint Week 2: Movie Management

### US3: Movie Management - Add New Movie
Administrator can add new movies to the system.

**Acceptance Criteria:**
- Administrator can provide movie details
- Movie is added to the system
- Movie details are stored in the database

**Linked FRs:** FR3

### US4: Movie Management - Update Movie Details
Administrator can update movie details.

**Acceptance Criteria:**
- Administrator can provide updated movie details
- Movie details are updated in the system
- Updated details are stored in the database

**Linked FRs:** FR3

## Sprint Week 3: Show Management

### US5: Show Scheduling
Administrator can schedule movie showtimes and assign them to specific halls.

**Acceptance Criteria:**
- Administrator can provide show scheduling details
- Show is scheduled and assigned to a hall
- Show details are stored in the database

**Linked FRs:** FR4

### US6: View Movies
Customers can view movie list and details.

**Acceptance Criteria:**
- Customers can view movie list
- Customers can view movie details
- Customers can view available showtimes

**Linked FRs:** FR5

## Sprint Week 4: Ticket Booking and History

### US7: Seat Selection
Customers can select available seats for a movie show.

**Acceptance Criteria:**
- Customers can view available seats
- Customers can select seats
- Selected seats are marked as booked

**Linked FRs:** FR6

### US8: Ticket Booking
Customers can book tickets for selected seats.

**Acceptance Criteria:**
- Customers can book tickets
- Booked seats are marked as booked
- Booking confirmation is provided

**Linked FRs:** FR7

### US9: Payment Processing
Customers can make payments for booked tickets.

**Acceptance Criteria:**
- Customers can provide payment details
- Payment is processed
- Payment confirmation is provided

**Linked FRs:** FR8

### US10: Ticket Generation
System generates a digital ticket after successful booking.

**Acceptance Criteria:**
- System generates a digital ticket
- Ticket is stored in the database
- Ticket is provided to the customer

**Linked FRs:** FR9

### US11: Booking History
Customers can view their booking history.

**Acceptance Criteria:**
- Customers can view booking history
- Booking history is accurate
- Booking history is stored in the database

**Linked FRs:** FR10
