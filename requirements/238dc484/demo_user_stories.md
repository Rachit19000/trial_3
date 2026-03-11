# User Stories: Movie Hall Management System

**Total User Stories:** 11
**Estimated Effort:** 28 days

## Sprint Week 1: User Authentication

### US1: User Registration
Allow customers to register using personal details such as name, email, and password.

**Acceptance Criteria:**
- User can provide name, email, and password
- User receives confirmation message upon successful registration
- User ID is generated and stored

**Linked FRs:** FR1

### US2: User Login
Allow registered users to log in securely.

**Acceptance Criteria:**
- User can provide email and password
- User receives login confirmation
- Session token is generated and stored

**Linked FRs:** FR2

## Sprint Week 2: Movie Management

### US3: Movie Management - Add New Movie
Administrator can add new movies.

**Acceptance Criteria:**
- Administrator can provide movie details
- Movie is added to the system
- Movie ID is generated and stored

**Linked FRs:** FR3

### US4: Movie Management - Update Movie Details
Administrator can update movie details.

**Acceptance Criteria:**
- Administrator can provide updated movie details
- Movie details are updated in the system
- Movie ID is validated and updated

**Linked FRs:** FR3

## Sprint Week 3: Show Management

### US5: Show Scheduling
Administrator can schedule movie showtimes and assign them to specific halls.

**Acceptance Criteria:**
- Administrator can provide show details
- Show is scheduled and assigned to a hall
- Show ID is generated and stored

**Linked FRs:** FR4

### US6: View Movies
Customers can view movie list, movie details, and available showtimes.

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
- Customers can book selected seats
- Booking is confirmed
- Booking ID is generated and stored

**Linked FRs:** FR7

### US9: Payment Processing
Customers can make payments for booked tickets.

**Acceptance Criteria:**
- Customers can make payments
- Payment is processed
- Booking status is updated to Paid

**Linked FRs:** FR8

### US10: Ticket Generation
System generates a digital ticket after successful booking.

**Acceptance Criteria:**
- Digital ticket is generated
- Ticket is linked to the booking
- Ticket is sent to the customer

**Linked FRs:** FR9

### US11: Booking History
Customers can view their booking history.

**Acceptance Criteria:**
- Customers can view booking history
- Booking history is displayed
- History includes booking details

**Linked FRs:** FR10
