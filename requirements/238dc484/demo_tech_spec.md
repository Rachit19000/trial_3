# Technical Specification

## 1. System Overview

**Project Name:** Movie Hall Management System

**Description:** A web-based application for managing movie schedules, seat bookings, ticket generation, and customer management.

**Architecture Pattern:** Microservices

### Key Design Decisions

- Use microservices for scalability and maintainability
- Implement RESTful APIs for communication between services
- Use a database for persistent storage

## 2. Data Model

### Entity: User

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the user |
| name | String | Name of the user |
| email | String | Email address of the user |
| password | String | Password of the user (hashed) |
| role | String | Role of the user (Admin/Customer) |

**Relationships:** Movie, Booking

### Entity: Movie

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the movie |
| title | String | Title of the movie |
| description | String | Description of the movie |
| duration | Integer | Duration of the movie in minutes |
| poster_url | String | URL of the movie poster |

**Relationships:** Show, Booking

### Entity: Show

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the show |
| movie_id | UUID | Foreign key to the Movie entity |
| hall_id | UUID | Foreign key to the Hall entity |
| start_time | Timestamp | Start time of the show |
| end_time | Timestamp | End time of the show |

**Relationships:** Hall, Booking

### Entity: Hall

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the hall |
| name | String | Name of the hall |
| seats | Integer | Total number of seats in the hall |

**Relationships:** Show, Seat

### Entity: Seat

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the seat |
| hall_id | UUID | Foreign key to the Hall entity |
| row | Integer | Row number of the seat |
| column | Integer | Column number of the seat |
| is_booked | Boolean | Indicates if the seat is booked |

**Relationships:** Booking

### Entity: Booking

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the booking |
| user_id | UUID | Foreign key to the User entity |
| show_id | UUID | Foreign key to the Show entity |
| seat_ids | Array<UUID> | Array of seat IDs booked for the show |
| total_amount | Decimal | Total amount for the booking |
| status | String | Status of the booking (Pending/Paid) |

**Relationships:** User, Show, Seat

## 3. API Design

| Method | Path | Description |
|--------|------|-------------|
| POST | `/users/register` | Register a new user |
| POST | `/users/login` | User login |
| GET | `/movies` | Get list of movies |
| GET | `/movies/{movie_id}` | Get movie details |
| GET | `/shows` | Get list of shows |
| GET | `/shows/{show_id}` | Get show details |
| GET | `/seats/{show_id}` | Get available seats for a show |
| POST | `/bookings` | Book seats for a show |
| GET | `/bookings/{booking_id}` | Get booking details |
| GET | `/bookings/history` | Get booking history |

### POST `/users/register`

Register a new user

**Request Body:** User registration details

**Response Body:** User registration confirmation

### POST `/users/login`

User login

**Request Body:** User login credentials

**Response Body:** User login confirmation

### GET `/movies`

Get list of movies

**Response Body:** List of movies

### GET `/movies/{movie_id}`

Get movie details

**Response Body:** Movie details

### GET `/shows`

Get list of shows

**Response Body:** List of shows

### GET `/shows/{show_id}`

Get show details

**Response Body:** Show details

### GET `/seats/{show_id}`

Get available seats for a show

**Response Body:** List of available seats

### POST `/bookings`

Book seats for a show

**Request Body:** Seat booking details

**Response Body:** Booking confirmation

### GET `/bookings/{booking_id}`

Get booking details

**Response Body:** Booking details

### GET `/bookings/history`

Get booking history

**Response Body:** List of booking history

## 4. Component Breakdown

### UserManagementService

**Responsibility:** Handles user registration and login

**Depends on:** UserService

### MovieService

**Responsibility:** Manages movie details and schedules

**Depends on:** UserService

### ShowService

**Responsibility:** Manages show schedules and seat availability

**Depends on:** MovieService, UserService

### BookingService

**Responsibility:** Manages seat booking and ticket generation

**Depends on:** ShowService, UserService

## 5. Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React |
| Backend | Node.js |
| Database | PostgreSQL |
| Infrastructure | AWS |

## 6. Risks & Mitigations

| Risk | Impact | Mitigation |
|------|--------|------------|
| Database performance issues | Slow response times | Optimize queries and use indexing |
| Security vulnerabilities | Data breaches | Implement secure authentication and encryption |
| Scalability issues | System crashes under high load | Use load balancers and auto-scaling |

## 7. Open Questions

- What is the exact payment gateway to be used?
- What is the expected load on the system?
- What is the backup and recovery plan for the database?
