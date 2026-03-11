# Technical Specification

## 1. System Overview

**Project Name:** Movie Hall Management System

**Description:** A web-based application for managing movie schedules, seat bookings, ticket generation, and customer management.

**Architecture Pattern:** Microservices

### Key Design Decisions

- Use microservices architecture for scalability and maintainability
- Implement RESTful APIs for service communication
- Use a database for persistent storage

## 2. Data Model

### Entity: User

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the user |
| name | String | Name of the user |
| email | String | Email address of the user |
| password | String | Hashed password of the user |
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
| total_amount | Decimal | Total amount for the booking |
| status | String | Status of the booking (Pending/Paid) |

**Relationships:** Seat

## 3. API Design

| Method | Path | Description |
|--------|------|-------------|
| POST | `/users/register` | Register a new user |
| POST | `/users/login` | Login a registered user |
| GET | `/movies` | Get a list of movies |
| GET | `/movies/{movie_id}` | Get details of a movie |
| POST | `/movies` | Add a new movie |
| PUT | `/movies/{movie_id}` | Update movie details |
| DELETE | `/movies/{movie_id}` | Remove a movie |
| POST | `/shows` | Schedule a new show |
| GET | `/shows` | Get a list of shows |
| GET | `/shows/{show_id}` | Get details of a show |
| GET | `/seats/{show_id}` | Get available seats for a show |
| POST | `/bookings` | Book seats for a show |
| GET | `/bookings` | Get booking history |

### POST `/users/register`

Register a new user

**Request Body:** name: String, email: String, password: String, role: String

**Response Body:** id: UUID, name: String, email: String, role: String

### POST `/users/login`

Login a registered user

**Request Body:** email: String, password: String

**Response Body:** token: String

### GET `/movies`

Get a list of movies

**Response Body:** [{id: UUID, title: String, description: String, duration: Integer}]

### GET `/movies/{movie_id}`

Get details of a movie

**Response Body:** {id: UUID, title: String, description: String, duration: Integer}

### POST `/movies`

Add a new movie

**Request Body:** title: String, description: String, duration: Integer

**Response Body:** {id: UUID, title: String, description: String, duration: Integer}

### PUT `/movies/{movie_id}`

Update movie details

**Request Body:** title: String, description: String, duration: Integer

**Response Body:** {id: UUID, title: String, description: String, duration: Integer}

### DELETE `/movies/{movie_id}`

Remove a movie

### POST `/shows`

Schedule a new show

**Request Body:** movie_id: UUID, hall_id: UUID, start_time: DateTime

**Response Body:** {id: UUID, movie_id: UUID, hall_id: UUID, start_time: DateTime}

### GET `/shows`

Get a list of shows

**Response Body:** [{id: UUID, movie_id: UUID, hall_id: UUID, start_time: DateTime}]

### GET `/shows/{show_id}`

Get details of a show

**Response Body:** {id: UUID, movie_id: UUID, hall_id: UUID, start_time: DateTime}

### GET `/seats/{show_id}`

Get available seats for a show

**Response Body:** [{id: UUID, row: Integer, column: Integer, is_booked: Boolean}]

### POST `/bookings`

Book seats for a show

**Request Body:** show_id: UUID, seat_ids: [UUID]

**Response Body:** {id: UUID, user_id: UUID, show_id: UUID, total_amount: Decimal, status: String}

### GET `/bookings`

Get booking history

**Response Body:** [{id: UUID, user_id: UUID, show_id: UUID, total_amount: Decimal, status: String}]

## 4. Component Breakdown

### User Management Service

**Responsibility:** Handles user registration, login, and management

**Depends on:** Database

### Movie Management Service

**Responsibility:** Handles movie addition, update, and deletion

**Depends on:** Database

### Show Management Service

**Responsibility:** Handles show scheduling and management

**Depends on:** Database

### Booking Service

**Responsibility:** Handles seat selection, booking, and payment processing

**Depends on:** Database

### Notification Service

**Responsibility:** Sends booking confirmation and payment confirmation emails

**Depends on:** Email Service

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
| Database performance issues | Slow response times | Optimize database queries, use indexing, and implement caching |
| Security vulnerabilities | Data breaches, unauthorized access | Implement secure authentication, use HTTPS, encrypt sensitive data |
| Scalability issues | System crashes under high load | Use load balancers, auto-scaling, and microservices architecture |

## 7. Open Questions

- What is the exact payment gateway to be used?
- How will the system handle multiple movie halls in different locations?
