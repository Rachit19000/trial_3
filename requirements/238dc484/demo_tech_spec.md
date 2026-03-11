# Technical Specification

## 1. System Overview

**Project Name:** Cab Booking System

**Description:** A web/mobile-based application for passengers to book cabs, track drivers, and manage payments. Drivers can accept ride requests and manage their availability. Administrators manage users, drivers, and system operations.

**Architecture Pattern:** Microservices

### Key Design Decisions

- Use microservices architecture for scalability and maintainability
- Implement real-time location tracking using websockets
- Use OAuth2 for secure user authentication

## 2. Data Model

### Entity: User

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the user |
| name | String | Full name of the user |
| email | String | Email address of the user |
| phone_number | String | Phone number of the user |
| password | String | Password of the user |
| role | String | Role of the user (Passenger, Driver, Admin) |

**Relationships:** Driver, Passenger, Admin

### Entity: Driver

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the driver |
| user_id | UUID | Foreign key to the User entity |
| availability_status | String | Availability status of the driver (Online, Offline) |

**Relationships:** User

### Entity: Ride

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the ride |
| pickup_location | String | Pickup location of the ride |
| destination_location | String | Destination location of the ride |
| status | String | Status of the ride (Pending, In Progress, Completed) |
| created_at | Timestamp | Timestamp when the ride was created |
| updated_at | Timestamp | Timestamp when the ride was last updated |

**Relationships:** Passenger, Driver

## 3. API Design

| Method | Path | Description |
|--------|------|-------------|
| POST | `/users/register` | Register a new user |
| POST | `/users/login` | Log in a user |
| POST | `/rides/book` | Book a cab |
| GET | `/rides/{ride_id}` | Get ride details |
| PUT | `/rides/{ride_id}/mark-as-completed` | Mark ride as completed |
| GET | `/drivers/availability` | Get driver availability |
| PUT | `/drivers/availability` | Update driver availability |
| GET | `/users/history` | Get user ride history |

### POST `/users/register`

Register a new user

**Request Body:** name, phone_number, password

**Response Body:** id, name, email, phone_number, role

### POST `/users/login`

Log in a user

**Request Body:** email, password

**Response Body:** access_token, user_id, role

### POST `/rides/book`

Book a cab

**Request Body:** pickup_location, destination_location

**Response Body:** id, pickup_location, destination_location, status

### GET `/rides/{ride_id}`

Get ride details

**Response Body:** id, pickup_location, destination_location, status, created_at, updated_at

### PUT `/rides/{ride_id}/mark-as-completed`

Mark ride as completed

**Response Body:** id, status

### GET `/drivers/availability`

Get driver availability

**Response Body:** id, availability_status

### PUT `/drivers/availability`

Update driver availability

**Request Body:** availability_status

**Response Body:** id, availability_status

### GET `/users/history`

Get user ride history

**Response Body:** id, pickup_location, destination_location, status, created_at, updated_at

## 4. Component Breakdown

### UserService

**Responsibility:** Handles user registration, login, and management

**Depends on:** UserService

### RideService

**Responsibility:** Handles ride booking, tracking, and completion

**Depends on:** UserService, RideService

### DriverService

**Responsibility:** Handles driver assignment, availability, and management

**Depends on:** UserService, DriverService

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
| High traffic during peak hours | System performance degradation | Implement load balancing and caching strategies |
| Data breaches | Loss of user trust and data | Implement strong encryption and regular security audits |

## 7. Open Questions

- What are the specific payment methods to be supported?
- How will user verification be handled for drivers?
