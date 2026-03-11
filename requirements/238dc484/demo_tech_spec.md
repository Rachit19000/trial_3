# Technical Specification

## 1. System Overview

**Project Name:** Movie Hall Management System

**Description:** A web-based application for managing movie schedules, seat bookings, ticket generation, and customer management.

**Architecture Pattern:** Microservices

### Key Design Decisions

- Use microservices architecture for scalability and maintainability
- Implement RESTful APIs for service communication
- Use a database for persistent storage of data

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

**Relationships:** Show, Booking

### Entity: Show

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the show |
| movie_id | UUID | Foreign key to the movie entity |
| hall_id | UUID | Foreign key to the hall entity |
| start_time | DateTime | Start time of the show |

**Relationships:** Seat, Booking

### Entity: Seat

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the seat |
| row | Integer | Row number of the seat |
| column | Integer | Column number of the seat |
| is_booked | Boolean | Indicates if the seat is booked |

**Relationships:** Show

### Entity: Booking

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the booking |
| user_id | UUID | Foreign key to the user entity |
| show_id | UUID | Foreign key to the show entity |
| seat_ids | Array<UUID> | Array of seat IDs for the booking |
| total_amount | Decimal | Total amount for the booking |
| status | String | Status of the booking (Pending/Paid) |

**Relationships:** User, Show

## 3. API Design

| Method | Path | Description |
|--------|------|-------------|
| POST | `/users/register` | Register a new user |
| POST | `/users/login` | Login a registered user |
| POST | `/movies` | Add a new movie |
| PUT | `/movies/{id}` | Update movie details |
| DELETE | `/movies/{id}` | Remove a movie |
| POST | `/shows` | Schedule a new show |
| GET | `/movies` | Get a list of movies |
| GET | `/shows/{id}` | Get show details |
| GET | `/seats/{show_id}` | Get available seats for a show |
| POST | `/bookings` | Book seats for a show |
| GET | `/bookings/{id}` | Get booking details |

### POST `/users/register`

Register a new user

**Request Body:** User details including name, email, and password

**Response Body:** Confirmation message and user ID

### POST `/users/login`

Login a registered user

**Request Body:** User credentials including email and password

**Response Body:** Login confirmation and session token

### POST `/movies`

Add a new movie

**Request Body:** Movie details including title, description, and duration

**Response Body:** Confirmation message and movie ID

### PUT `/movies/{id}`

Update movie details

**Request Body:** Updated movie details

**Response Body:** Confirmation message

### DELETE `/movies/{id}`

Remove a movie

**Response Body:** Confirmation message

### POST `/shows`

Schedule a new show

**Request Body:** Show details including movie ID, hall ID, and start time

**Response Body:** Confirmation message and show ID

### GET `/movies`

Get a list of movies

**Response Body:** List of movies

### GET `/shows/{id}`

Get show details

**Response Body:** Show details including movie, hall, and start time

### GET `/seats/{show_id}`

Get available seats for a show

**Response Body:** List of available seats

### POST `/bookings`

Book seats for a show

**Request Body:** Selected seat IDs

**Response Body:** Confirmation message and booking ID

### GET `/bookings/{id}`

Get booking details

**Response Body:** Booking details including user, show, and seat IDs

## 4. Component Breakdown

### UserService

**Responsibility:** Handles user registration, login, and authentication

**Depends on:** UserService

### MovieService

**Responsibility:** Manages movie details and scheduling

**Depends on:** UserService, ShowService

### ShowService

**Responsibility:** Manages show scheduling and seat availability

**Depends on:** SeatService, MovieService

### SeatService

**Responsibility:** Manages seat booking and availability

**Depends on:** ShowService

### BookingService

**Responsibility:** Manages booking creation and status updates

**Depends on:** UserService, ShowService, SeatService

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
| Database performance issues | High | Implement indexing and caching strategies |
| Security vulnerabilities | High | Regular security audits and use of secure coding practices |
| Scalability issues | High | Use microservices architecture and auto-scaling |

## 7. Open Questions

- What is the exact payment gateway to be used?
- What are the exact requirements for the digital ticket generation?
