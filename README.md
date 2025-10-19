# Airbnb Clone Backend

This is a backend service for an Airbnb Clone built with Django, Django REST Framework, PostgreSQL, GraphQL, Celery, Redis, and Docker.  
It provides APIs for managing users, properties, bookings, payments, and reviews.

## Feature Breakdown

- User registration and authentication  
- Property creation, update, and management  
- Booking system with check-in and check-out management  
- Secure payment processing  
- User reviews and property ratings  
- Database indexing and caching for performance optimization  

## Project Goals

- Build a scalable and secure backend for property rental and management.  
- Implement core Airbnb functionalities through REST and GraphQL APIs.  
- Ensure efficient data retrieval and storage using PostgreSQL and Redis.  
- Enable smooth collaboration through CI/CD and containerized development.

## Team Roles

**Backend Developer**  
Implements REST and GraphQL APIs, manages database models, and handles business logic.

**Database Administrator (DBA)**  
Designs schema, manages indexing, backups, and ensures optimal database performance.

**DevOps Engineer**  
Configures Docker environments, manages CI/CD pipelines, and monitors backend services.

**QA Engineer**  
Tests API endpoints, verifies backend stability, and ensures adherence to quality standards.

**Project Manager**  
Coordinates development tasks, manages timelines, and ensures milestone delivery.

## Technology Stack

**Django**: High-level Python framework for building the RESTful API.  
**Django REST Framework**: Simplifies creation and management of REST APIs.  
**PostgreSQL**: Relational database for structured and reliable data storage.  
**GraphQL**: Enables flexible and efficient client-side querying.  
**Celery**: Handles asynchronous tasks like notifications and background processing.  
**Redis**: Used for caching, task queuing, and session management.  
**Docker**: Provides isolated and consistent deployment environments.  
**CI/CD Pipelines**: Automates testing, building, and deployment processes.

## Database Design

### Entities and Fields

**Users**  
Fields: `user_id`, `first_name`, `last_name`, `email (unique)`, `password`, `phone_number`, `profile_picture`, `is_host`, `address`, `verified`, `created_at`, `updated_at`  
→ A user can create multiple properties and bookings.

**Properties**  
Fields: `property_id`, `title`, `description`, `price_per_night`, `max_guests`, `num_bedrooms`, `num_bathrooms`, `address`, `latitude`, `longitude`, `owner_id`, `is_available`, `created_at`, `updated_at`  
→ Each property belongs to one user (the host).

**Bookings**  
Fields: `booking_id`, `user_id (guest)`, `property_id`, `start_date`, `end_date`, `total_price`, `status`, `created_at`, `updated_at`  
→ Each booking connects a guest to a property.

**Reviews**  
Fields: `review_id`, `user_id`, `property_id`, `rating`, `comment`, `created_at`  
→ Each review belongs to one user and one property.

**Payments**  
Fields: `payment_id`, `booking_id`, `amount`, `status`, `transaction_date`  
→ Each payment is tied to a specific booking.

### Relationships

- One User → Many Properties  
- One Property → Many Bookings  
- One Booking → One Payment  
- One Property → Many Reviews  

## API Security

Security measures include:

**Authentication**: Token or JWT-based authentication for user sessions.  
**Authorization**: Role-based access control to restrict sensitive endpoints.  
**Input Validation**: Prevents SQL injection and malformed data inputs.  
**Rate Limiting**: Protects APIs from abuse and excessive requests.  
**Secure Payments**: Uses HTTPS and encryption for all payment transactions.

**Why it matters:**  
These measures ensure data protection, transaction security, and user trust.

## CI/CD Pipeline

**Definition:**  
Continuous Integration and Continuous Deployment (CI/CD) automate testing, building, and deploying the backend application.

**Tools:**  
- **GitHub Actions:** Runs automated tests and build workflows.  
- **Docker:** Containerizes the backend for uniform development and production environments.  
- **AWS / Render / DigitalOcean:** Potential platforms for automated deployment.

**Benefits:**  
- Faster feedback for developers.  
- Reduced manual deployment errors.  
- Reliable and reproducible releases.
