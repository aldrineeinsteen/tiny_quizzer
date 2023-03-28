# Architecture Documentation

## Overview

Tiny Quizzer's architecture consists of a frontend built using Flutter for cross-platform mobile app compatibility and a backend implemented in Python using the Flask web framework. The backend serves as a RESTful API, which the frontend communicates with to request and receive data.

```mermaid
graph TB
  subgraph Runtime
    A[Frontend - Flutter] --> B[Backend - Flask]
    B --> C[AI Model - GPT-3]
    B --> D[MongoDB Database]
    E[Web Server] --> B
  end
  subgraph Tiny Quizzer
    G[Continuous Integration & Deployment - GitLab CI/CD] --> Runtime
  end

  ```

## Frontend

### Flutter

-   The frontend is built using the Flutter framework, which enables cross-platform app development for Android and iOS.
-   The Dart programming language is used to develop the UI and handle user interactions.
-   The `http` package is used for making API calls to the backend.

## Backend

### Flask

-   The backend is implemented in Python using the Flask web framework.
-   The Flask app exposes RESTful API endpoints for the frontend to interact with.
-   The backend handles user authentication, data storage, and AI-powered question generation.

### AI Question Generation

-   The OpenAI GPT-3 model is utilized to generate questions based on user preferences and performance.
-   The model is fine-tuned for generating questions specific to the 11+ exams and other related tests.

### Data Storage

-   A PostgreSQL database is used to store user data, including profiles, quiz history, and performance analytics.
-   SQLAlchemy, an Object Relational Mapper (ORM), is used to interact with the database from the Flask app.

## Deployment and Infrastructure

### Web Server

-   The Flask app is deployed on a web server using Gunicorn, a WSGI HTTP server for Python applications.
-   Nginx is used as a reverse proxy to handle incoming requests and route them to the appropriate Gunicorn worker processes.

### Cloud Services

-   The application is hosted on a cloud provider such as Heroku, AWS, or DigitalOcean for scalability and reliability.
-   Cloud-based storage (e.g., AWS S3) is used to store static files, such as images and documents.

### Continuous Integration and Deployment

-   GitLab CI/CD is used to automate the testing and deployment process.
-   The pipeline includes steps for building the Flutter app, running backend tests, and deploying the application to the cloud provider.
