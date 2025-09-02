# Twitch-like Streaming Platform

A simplified Twitch-like streaming platform built with Spring Boot backend and React frontend, featuring real-time game streaming data integration, user authentication, and personalized content recommendations.

## Project Structure

```
twitch/          # Backend (Spring Boot)
twitchfe/        # Frontend (React)
```

## Core Features

### Backend Features
- **User Authentication**: Session-based authentication with Spring Security and OAuth2
- **Game Data Integration**: Real-time integration with Twitch API for games, streams, videos, and clips
- **Favorites Management**: User bookmarking system for favorite content
- **Recommendation System**: Personalized content recommendations based on user preferences
- **RESTful APIs**: 5 core endpoints for user management, game search, favorites, and recommendations

### Frontend Features
- **Responsive UI**: Modern interface built with React and Ant Design
- **User Authentication**: Login/registration forms with session management
- **Content Display**: Real-time streaming data presentation
- **Search Functionality**: Game and content search capabilities
- **Favorites Management**: User-friendly bookmarking interface

## Technology Stack

### Backend
- **Framework**: Spring Boot 3.5.0
- **Language**: Java 21
- **Security**: Spring Security with OAuth2
- **Database**: MySQL with Spring Data JDBC
- **External API**: Spring Cloud OpenFeign for Twitch API integration
- **Caching**: Spring Data Caching with Caffeine
- **Testing**: JUnit with Mockito
- **Containerization**: Docker with multi-stage builds
- **Cloud Deployment**: AWS (ECR, AppRunner, RDS)

### Frontend
- **Framework**: React 19.1.0
- **UI Library**: Ant Design 4.24.16
- **Testing**: React Testing Library
- **Build Tool**: Create React App

## Architecture

### Backend Architecture
- **Controller Layer**: REST API endpoints handling HTTP requests
- **Service Layer**: Business logic implementation
- **Repository Layer**: Data access with Spring Data JDBC
- **External Integration**: Twitch API client for real-time data
- **Security Layer**: Authentication and authorization

### Database Schema
- `users`: User account information
- `authorities`: User roles and permissions
- `items`: Streaming content data (videos, clips, streams)
- `favorite_records`: User bookmark relationships

## Getting Started

### Prerequisites
- Java 21
- Node.js 16+
- MySQL 8.0+
- Docker (optional)

### Backend Setup
```bash
cd twitch
./gradlew bootRun
```

### Frontend Setup
```bash
cd twitchfe
npm install
npm start
```

### Database Setup
The application automatically initializes the database schema on startup using the `database-init.sql` script.

## API Endpoints

- `POST /register` - User registration
- `GET /game` - Get games (top games or search by name)
- `GET /search` - Search items by game ID
- `GET /favorite` - Get user favorites
- `POST /favorite` - Add item to favorites
- `DELETE /favorite` - Remove item from favorites
- `GET /recommendation` - Get personalized recommendations

## Deployment

The application is containerized using Docker and deployed to AWS:
- **Container Registry**: AWS ECR
- **Application Platform**: AWS AppRunner
- **Database**: AWS RDS (MySQL)

## Testing

### Backend Tests
```bash
cd twitch
./gradlew test
```

### Frontend Tests
```bash
cd twitchfe
npm test
```

## Key Implementation Details

- **Authentication**: Session-based with Spring Security form login
- **External API Integration**: OAuth2 client credentials flow for Twitch API
- **Caching Strategy**: 1-minute TTL for external API responses
- **Error Handling**: Global exception handler with proper HTTP status codes
- **Database**: Relational design with foreign key constraints
- **Frontend-Backend Communication**: RESTful APIs with JSON data exchange
