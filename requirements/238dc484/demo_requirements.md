Cab Booking System
1. Introduction
1.1 Purpose

The purpose of the Cab Booking System is to allow users to book cabs online for traveling from one location to another. The system connects passengers with available drivers and manages bookings, payments, and ride history.

1.2 Scope

The system will enable users to register, book rides, track drivers, and make payments. Drivers can accept ride requests and manage their availability. Administrators manage users, drivers, and system operations.

1.3 Definitions

Passenger – User who books the cab.

Driver – Person who accepts ride requests and provides transportation.

Ride Request – Request created by a passenger to book a cab.

Trip – Completed journey from pickup to destination.

2. Overall Description
2.1 Product Perspective

The Cab Booking System will be a web/mobile-based application connected to a backend server and database to manage users, drivers, rides, and payments.

2.2 Product Functions

Major system functions include:

User registration and login

Cab booking

Driver allocation

Ride tracking

Payment processing

Ride history management

2.3 User Classes
User Type	Description
Passenger	Books cabs and makes payments
Driver	Accepts ride requests and completes trips
Admin	Manages drivers, users, and ride data
2.4 Operating Environment

Mobile app / Web browser

Backend server (Node.js / Java / Python)

Database (MySQL / PostgreSQL)

3. Functional Requirements
FR1: User Registration

The system shall allow passengers to register using name, phone number, and password.

FR2: User Login

The system shall allow registered users to log in securely.

FR3: Cab Booking

Passengers shall be able to book a cab by entering pickup and destination locations.

FR4: Driver Assignment

The system shall assign the nearest available driver to the passenger.

FR5: Ride Tracking

Passengers shall be able to track the driver’s location during the ride.

FR6: Ride Completion

Drivers shall mark the ride as completed after reaching the destination.

FR7: Payment Processing

Passengers shall be able to pay through online payment methods or cash.

FR8: Ride History

Passengers shall be able to view their previous ride details.

FR9: Driver Availability

Drivers shall be able to update their availability status (online/offline).

4. Non-Functional Requirements
NFR1: Performance

The system should process booking requests within a few seconds.

NFR2: Security

User data and payment information must be securely stored.

NFR3: Usability

The system interface should be simple and easy to use.

NFR4: Reliability

The system should provide accurate driver allocation and ride tracking.

NFR5: Scalability

The system should support a large number of users and ride requests.

5. System Features
5.1 User Management

Register and manage passengers and drivers.

5.2 Booking System

Request rides.

Assign drivers automatically.

5.3 Ride Management

Track rides.

Record trip details.

5.4 Payment System

Handle fare calculation and payments.

6. External Interface Requirements
6.1 User Interface

Mobile or web interface for passengers and drivers.

6.2 Database Interface

Stores data such as:

User accounts

Driver information

Ride details

Payment records

7. Constraints

GPS required for location tracking.

Internet connection required for booking.

Drivers must be verified before joining the system.