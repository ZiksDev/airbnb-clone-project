# airbnb-clone-project

The Airbnb Clone Project is a full-stack application that simulates a booking platform like Airbnb. It focuses on backend systems, database design, APIs, and security, helping learners grasp complex architectures, workflows, and teamwork while building a scalable web app.

# Project Goals

1-User Management: Secure registration, login, and profiles

2-Property Management: Add, update, and view listings

3-Booking System: Reserve and manage property bookings

4-Payments: Process and record transactions

5-Reviews: Leave ratings and feedback

6-Data Optimization: Improve database speed and storage

# Technology Stack

1-Django: A high-level Python web framework used for building the RESTful API.

2-Django REST Framework: Provides tools for creating and managing RESTful APIs.

3-PostgreSQL: A powerful relational database used for data storage.

4-GraphQL: Allows for flexible and efficient querying of data.

5-Celery: For handling asynchronous tasks such as sending notifications or processing payments.

6-Redis: Used for caching and session management.

7-Docker: Containerization tool for consistent development and deployment environments.

8-CI/CD Pipelines: Automated pipelines for testing and deploying code changes.

# Team Roles

Backend Developer: Responsible for implementing API endpoints, database schemas, and business logic/
Database Administrator: Manages database design, indexing, and optimizations/
DevOps Engineer: Handles deployment, monitoring, and scaling of the backend services/
QA Engineer: Ensures the backend functionalities are thoroughly tested and meet quality standards.

# Database Design

1. Users

Fields

id (unique identifier)

name (full name)

email (unique, for authentication)

password_hash (securely stored password)

role (guest, host, or admin)

Relationships

A user can list multiple properties (if host).

A user can make multiple bookings (as a guest).

A user can leave multiple reviews.

2. Properties

Fields

id (unique identifier)

title (property name)

description (details about the property)

price_per_night (numeric)

location (city, address, or coordinates)

Relationships

A property belongs to one user (host).

A property can have multiple bookings.

A property can have multiple reviews.

3. Bookings

Fields

id (unique identifier)

user_id (guest making the booking)

property_id (linked property)

start_date

end_date

status (pending, confirmed, canceled)

Relationships

A booking belongs to one user (guest).

A booking belongs to one property.

A booking may be linked to a payment.

4. Payments

Fields

id (unique identifier)

booking_id (associated booking)

amount (total charged)

payment_method (card, PayPal, etc.)

status (success, failed, refunded)

Relationships

A payment belongs to one booking.

A booking can have one or more payments (e.g., deposit + balance).

5. Reviews

Fields

id (unique identifier)

user_id (guest writing the review)

property_id (reviewed property)

rating (1–5 stars)

comment (text feedback)

Relationships

A review belongs to one user (guest).

A review belongs to one property.
