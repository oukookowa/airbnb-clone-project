# airbnb-clone-project

## Project Overview
### Objective
The backend for the Airbnb Clone project is designed to provide a robust and scalable foundation for managing user interactions, property listings, bookings, and payments. This backend will support various functionalities required to mimic the core features of Airbnb, ensuring a seamless experience for users and hosts. The project encapsulates modern software technology practices, ensuring the app is secure, scalable, and efficient.

Tech stack: Django, Django REST Framework, PostgreSQL, GraphQL, GitHub, Docker, Redis, Celery, CI/CD pipelines.

### Goals
User Management: Implement a secure system for user registration, authentication, and profile management.

Property Management: Develop features for property listing creation, updates, and retrieval.

Booking System: Create a booking mechanism for users to reserve properties and manage booking details.

Payment Processing: Integrate a payment system to handle transactions and record payment details.

Review System: Allow users to leave reviews and ratings for properties.

Data Optimization: Ensure efficient data retrieval and storage through database optimizations.

## Features Overview
1. API Documentation
OpenAPI Standard: The backend APIs are documented using the OpenAPI standard to ensure clarity and ease of integration.
Django REST Framework: Provides a comprehensive RESTful API for handling CRUD operations on user and property data.
GraphQL: Offers a flexible and efficient query mechanism for interacting with the backend.

2. User Authentication
Endpoints: /users/, /users/{user_id}/
Features: Register new users, authenticate, and manage user profiles.

3. Property Management
Endpoints: /properties/, /properties/{property_id}/
Features: Create, update, retrieve, and delete property listings.

4. Booking System
Endpoints: /bookings/, /bookings/{booking_id}/
Features: Make, update, and manage bookings, including check-in and check-out details.

5. Payment Processing
Endpoints: /payments/
Features: Handle payment transactions related to bookings.

6. Review System
Endpoints: /reviews/, /reviews/{review_id}/
Features: Post and manage reviews for properties.

7. Database Optimizations
Indexing: Implement indexes for fast retrieval of frequently accessed data.
Caching: Use caching strategies to reduce database load and improve performance.

## Team Roles
Business Analyst - Transforms customers' business needs into requirements.

Product Owner - Ensures that the final product meets customer requirements. Holds the responsibility for a product's success than any other member.

Project Manager - Ensures that a project is delivered on time and within budget.

UI/UX Designer - Ensures the best user experience and high conversion rates.

Software Architect - Selects appropriate tools and platforms to implement the product vision, sets code quality standards, and does code reviews.

Software Developer - Solves problems emerging during the development lifecycle and engineers the product.

Quality Assurance - Spots functional and non-functional defects to ensure an application performs according to requirements.

Test automation engineer - Writes and maintains test scripts for automated testing.

DevOps engineer - Facilitates cooperation between development and operations teams. Builds continuous integration and continuous delivery (CI/CD) pipelines for faster delivery.

## Technology Stack
Django - A high-level Python web framework used for building a RESTful API.

Django REST Framework - Provide tools for building robust RESTful APIs.

PostgreSQL - A powerful relational database for storing structured data.

GitHub - A platform for collaboration between teams.

Git - Used for version control.

Docker - A Containerization tool for consistent development and deployment environments.

CI/CD Pipelines - Automated pipelines for testing and deploying code changes.

GraphQL - Allows for flexible and efficient querying of data.

Celery - For handling asynchronous tasks such as sending notifications or processing payments.

## API Documentation Overview
REST API: Detailed documentation available through the OpenAPI standard, including endpoints for users, properties, bookings, reviews, and payments.
GraphQL API: Provides a flexible query language for retrieving and manipulating data.

## Endpoints Overview
REST API Endpoints

**Users:**

GET /users/ - List all users

POST /users/ - Create a new user

GET /users/{user_id}/ - Retrieve a specific user

PUT /users/{user_id}/ - Update a specific user

DELETE /users/{user_id}/ - Delete a specific user

**Properties:**

GET /properties/ - List all properties

POST /properties/ - Create a new property

GET /properties/{property_id}/ - Retrieve a specific property

PUT /properties/{property_id}/ - Update a specific property

DELETE /properties/{property_id}/ - Delete a specific property

**Bookings**:

GET /bookings/ - List all bookings

POST /bookings/ - Create a new booking

GET /bookings/{booking_id}/ - Retrieve a specific booking

PUT /bookings/{booking_id}/ - Update a specific booking

DELETE /bookings/{booking_id}/ - Delete a specific booking

**Payments:**

POST /payments/ - Process a payment

**Reviews:**

GET /reviews/ - List all reviews

POST /reviews/ - Create a new review

GET /reviews/{review_id}/ - Retrieve a specific review

PUT /reviews/{review_id}/ - Update a specific review

DELETE /reviews/{review_id}/ - Delete a specific review

## Database Design
**Users:**

id: Primary Key

name: Full name of the user

email: Unique email address (used for login)

password: Hashed user password

user_type: Indicates whether the user is a guest or host

**Properties:**

id: Primary Key

owner_id: Foreign Key referencing Users.id (host)

title: Name of the property

description: Details about the property

location: Address or coordinates

**Bookings:**

id: Primary Key

owner_id: Foreign Key referencing Users.id (host)

title: Name of the property

description: Details about the property

location: Address or coordinates

**Reviews:**

id: Primary Key

user_id: Foreign Key referencing Users.id

property_id: Foreign Key referencing Properties.id

rating: Numeric score (e.g., 1-5)

comment: Text feedback

**Payments:**

id: Primary Key

booking_id: Foreign Key referencing Bookings.id

amount: Total payment amount

payment_status: e.g., "completed", "pending", "failed"

payment_date: Timestamp of the payment

**Entity Relationships:**

A user can be both a host and a guest.

A user can own multiple properties (one-to-many).

A property can have many bookings (one-to-many).

A booking is made by a guest for a property (many-to-one).

A user can leave multiple reviews for different properties (one-to-many).

Each booking has one payment (one-to-one).

