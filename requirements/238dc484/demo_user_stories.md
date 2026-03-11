# User Stories: Movie Hall Management System

**Total User Stories:** 10
**Estimated Effort:** 20 days

## Sprint Week 1: Sprint 1

### US1: Register a new user
As a customer, I want to register with the system using my personal details so that I can book movie tickets.

**Acceptance Criteria:**
- User can provide name, email, and password during registration.
- System validates email format and password strength.
- User receives a confirmation message upon successful registration.

**Linked FRs:** FR1

### US2: Log in a registered user
As a customer, I want to log in to the system using my credentials so that I can access my account and book movie tickets.

**Acceptance Criteria:**
- User can provide email and password for login.
- System validates user credentials.
- User receives a session token upon successful login.

**Linked FRs:** FR2

## Sprint Week 2: Sprint 2

### US3: Add a new movie
As an administrator, I want to add a new movie to the system so that it can be shown in the movie listings.

**Acceptance Criteria:**
- Administrator can provide movie title, description, and duration.
- System validates movie details.
- Administrator receives a confirmation message upon successful addition.

**Linked FRs:** FR3

### US4: Schedule a new show
As an administrator, I want to schedule a new show for a movie in a specific hall so that customers can book tickets.

**Acceptance Criteria:**
- Administrator can provide show start time and assign it to a hall.
- System validates show details.
- Administrator receives a confirmation message upon successful scheduling.

**Linked FRs:** FR4

## Sprint Week 3: Sprint 3

### US5: View movie list and details
As a customer, I want to view the list of movies and their details so that I can choose a movie to watch.

**Acceptance Criteria:**
- Customer can view a list of movies.
- Customer can view movie details including title, description, and duration.
- Customer can view available showtimes for each movie.

**Linked FRs:** FR5

### US6: Select available seats for a movie show
As a customer, I want to select available seats for a movie show so that I can book my preferred seats.

**Acceptance Criteria:**
- Customer can view available seats for a show.
- Customer can select seats and add them to the booking.
- System validates seat selection and updates seat availability.

**Linked FRs:** FR6

## Sprint Week 4: Sprint 4

### US7: Book tickets for selected seats
As a customer, I want to book tickets for selected seats so that I can confirm my movie show.

**Acceptance Criteria:**
- Customer can book tickets for selected seats.
- System generates a booking ID and updates seat availability.
- Customer receives a confirmation message upon successful booking.

**Linked FRs:** FR7

### US8: Process payment for booked tickets
As a customer, I want to process payment for booked tickets so that I can confirm my booking.

**Acceptance Criteria:**
- Customer can choose a payment gateway.
- System processes payment and updates booking status.
- Customer receives a confirmation message upon successful payment.

**Linked FRs:** FR8

### US9: Generate a digital ticket after successful booking
As a customer, I want to receive a digital ticket after booking my movie show so that I can access my ticket.

**Acceptance Criteria:**
- System generates a digital ticket with booking details.
- Customer can download the digital ticket.
- System updates the booking status to Paid.

**Linked FRs:** FR9

### US10: View booking history
As a customer, I want to view my booking history so that I can track my past bookings.

**Acceptance Criteria:**
- Customer can view a list of past bookings.
- Customer can view details of each booking.
- System updates booking history.

**Linked FRs:** FR10
