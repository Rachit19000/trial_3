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
| name | String | Name of the user |
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
| driver_id | UUID | Foreign key to the Driver entity |
| passenger_id | UUID | Foreign key to the User entity (Passenger) |
| payment_method | String | Payment method used for the ride |

**Relationships:** Driver, Passenger

## 3. API Design

| Method | Path | Description |
|--------|------|-------------|
| POST | `/users/register` | Register a new user |
| POST | `/users/login` | Login a registered user |
| POST | `/rides/book` | Book a ride |
| GET | `/rides/{ride_id}` | Get ride details |
| PUT | `/drivers/{driver_id}/status` | Update driver availability status |

### POST `/users/register`

Register a new user

**Request Body:** name, phone_number, password

**Response Body:** id, name, phone_number, role

### POST `/users/login`

Login a registered user

**Request Body:** phone_number, password

**Response Body:** id, name, phone_number, role

### POST `/rides/book`

Book a ride

**Request Body:** pickup_location, destination_location

**Response Body:** id, pickup_location, destination_location, status, driver_id, passenger_id, payment_method

### GET `/rides/{ride_id}`

Get ride details

**Response Body:** id, pickup_location, destination_location, status, driver_id, passenger_id, payment_method

### PUT `/drivers/{driver_id}/status`

Update driver availability status

**Request Body:** availability_status

**Response Body:** id, availability_status

## 4. Component Breakdown

### UserManagementService

**Responsibility:** Handles user registration, login, and management

**Depends on:** UserService, DriverService

### RideService

**Responsibility:** Handles ride booking, tracking, and completion

**Depends on:** UserService, DriverService

### PaymentService

**Responsibility:** Handles payment processing

**Depends on:** UserService

### DriverService

**Responsibility:** Handles driver allocation and management

**Depends on:** UserService

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
| Scalability issues with high user load | System performance degradation | Implement load balancing and auto-scaling on AWS |
| Data breaches due to insecure storage | Loss of user trust and data exposure | Use encryption and secure storage practices |

## 7. Open Questions

- What are the exact payment methods to be supported?
- How will GPS data be integrated for location tracking?
