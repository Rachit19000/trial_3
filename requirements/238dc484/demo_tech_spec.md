# Technical Specification

## 1. System Overview

**Project Name:** Library Management System

**Description:** A web-based application designed to automate the management of library activities such as managing books, issuing and returning books, and maintaining member records.

**Architecture Pattern:** Microservices

### Key Design Decisions

- Use microservices for scalability and maintainability
- Implement RESTful APIs for easy integration
- Use a relational database for data persistence

## 2. Data Model

### Entity: Member

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the member |
| username | String | Username for the member |
| password | String | Password for the member |
| name | String | Full name of the member |
| email | String | Email address of the member |
| borrowed_books | List<Book> | List of books currently borrowed by the member |

**Relationships:** borrowed_books

### Entity: Book

| Field | Type | Description |
|-------|------|-------------|
| id | UUID | Unique identifier for the book |
| title | String | Title of the book |
| author | String | Author of the book |
| isbn | String | ISBN of the book |
| category | String | Category of the book |
| available | Boolean | Indicates if the book is available for borrowing |
| issued_to | Member | Member who currently has the book issued |

**Relationships:** issued_to

## 3. API Design

| Method | Path | Description |
|--------|------|-------------|
| POST | `/api/member/register` | Register a new member |
| POST | `/api/member/login` | Login a registered member |
| POST | `/api/book/add` | Add a new book |
| PUT | `/api/book/update/{id}` | Update book details |
| DELETE | `/api/book/delete/{id}` | Delete a book |
| GET | `/api/book/available` | Get a list of available books |
| POST | `/api/book/issue/{member_id}` | Issue a book to a member |
| POST | `/api/book/return/{member_id}` | Return a book from a member |
| GET | `/api/member/borrowed/{member_id}` | Get a list of books currently borrowed by a member |

### POST `/api/member/register`

Register a new member

**Request Body:** username, password, name, email

**Response Body:** id, username, name, email

### POST `/api/member/login`

Login a registered member

**Request Body:** username, password

**Response Body:** id, username, name, email

### POST `/api/book/add`

Add a new book

**Request Body:** title, author, isbn, category

**Response Body:** id, title, author, isbn, category

### PUT `/api/book/update/{id}`

Update book details

**Request Body:** title, author, isbn, category

**Response Body:** id, title, author, isbn, category

### DELETE `/api/book/delete/{id}`

Delete a book

**Response Body:** id

### GET `/api/book/available`

Get a list of available books

**Response Body:** [{id, title, author, isbn, category, available}]

### POST `/api/book/issue/{member_id}`

Issue a book to a member

**Request Body:** book_id

**Response Body:** id, title, author, isbn, category, issued_to

### POST `/api/book/return/{member_id}`

Return a book from a member

**Request Body:** book_id

**Response Body:** id, title, author, isbn, category, issued_to

### GET `/api/member/borrowed/{member_id}`

Get a list of books currently borrowed by a member

**Response Body:** [{id, title, author, isbn, category, issued_to}]

## 4. Component Breakdown

### MemberService

**Responsibility:** Handles member registration, login, and profile management

**Depends on:** UserService

### BookService

**Responsibility:** Handles book management, including adding, updating, and deleting books

**Depends on:** BookRepository

### BookRepository

**Responsibility:** Manages book data persistence and retrieval

**Depends on:** Database

### UserService

**Responsibility:** Manages user authentication and authorization

**Depends on:** UserRepository

### UserRepository

**Responsibility:** Manages user data persistence and retrieval

**Depends on:** Database

### Database

**Responsibility:** Manages data storage and retrieval for the application

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
| Data loss due to database failure | High | Implement regular backups and use a robust database management system |
| Security vulnerabilities in the application | High | Conduct regular security audits and use secure coding practices |

## 7. Open Questions

- What is the exact format for the password field?
- How should the system handle concurrent book issuance and return requests?
- What is the maximum number of books a member can borrow?
