# User Stories: Movie Hall Management System

**Total User Stories:** 11
**Estimated Effort:** 32 days

## Sprint Week 1: User Authentication

### US1: User Registration
Allow customers to register using personal details such as name, email, and password.

**Acceptance Criteria:**
- Customers can provide their name, email, and password during registration.
- Registration process is secure and user details are stored in the database.
- Duplicate email addresses are not allowed during registration.

**Linked FRs:** FR1

### US2: User Login
Allow registered users to log in securely.

**Acceptance Criteria:**
- Users can log in using their email and password.
- Login process is secure and user details are not exposed.
- Users are redirected to the dashboard upon successful login.

**Linked FRs:** FR2

## Sprint Week 2: Movie Management

### US3: Movie Management - Add New Movie
Allow administrators to add new movies.

**Acceptance Criteria:**
- Administrators can add new movies with details such as title, description, and duration.
- New movies are stored in the database.
- Movies are displayed on the movie list page.

**Linked FRs:** FR3

### US4: Movie Management - Update Movie Details
Allow administrators to update movie details.

**Acceptance Criteria:**
- Administrators can update existing movies with new details.
- Updated movie details are stored in the database.
- Updated movies are displayed on the movie list page.

**Linked FRs:** FR3

## Sprint Week 3: Show Management

### US5: Show Scheduling
Allow administrators to schedule movie showtimes and assign them to specific halls.

**Acceptance Criteria:**
- Administrators can schedule showtimes for movies in specific halls.
- Showtimes are stored in the database.
- Showtimes are displayed on the show list page.

**Linked FRs:** FR4

### US6: View Movies - Movie List
Allow customers to view the list of movies.

**Acceptance Criteria:**
- Customers can view the list of movies available in the system.
- Movie list includes title, description, and showtimes.
- Movie list is updated in real-time.

**Linked FRs:** FR5

## Sprint Week 4: Booking and Payment

### US7: Seat Selection
Allow customers to select available seats for a movie show.

**Acceptance Criteria:**
- Customers can view available seats for a specific show.
- Customers can select seats for booking.
- Selected seats are marked as booked.

**Linked FRs:** FR6

### US8: Ticket Booking
Allow customers to book tickets for selected seats.

**Acceptance Criteria:**
- Customers can book tickets for selected seats.
- Booked seats are marked as booked.
- Booking confirmation is sent to the customer.

**Linked FRs:** FR7

### US9: Payment Processing
Allow customers to make payments for booked tickets.

**Acceptance Criteria:**
- Customers can make payments using a secure payment gateway.
- Payment is processed and stored in the database.
- Payment confirmation is sent to the customer.

**Linked FRs:** FR8

### US10: Ticket Generation
Generate a digital ticket after successful booking.

**Acceptance Criteria:**
- Digital tickets are generated after successful booking.
- Tickets are stored in the database.
- Tickets are sent to the customer via email.

**Linked FRs:** FR9

### US11: Booking History
Allow customers to view their booking history.

**Acceptance Criteria:**
- Customers can view their booking history.
- Booking history includes details of all bookings.
- Booking history is updated in real-time.

**Linked FRs:** FR10
