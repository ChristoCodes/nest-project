# Technical Evaluation Project - Task Manager

## Project Overview
Full-stack task management application with user authentication, built for technical skills assessment using:
- **Backend**: Laravel 10 REST API
- **Frontend**: React 18 + Material-UI (MUI)
- **Infrastructure**: Docker + MySQL + SendGrid/MailHog

## Technologies Stack
![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)

## Prerequisites
- Docker 20.10+
- Docker Compose 2.15+
- Git 2.35+

## Getting Started

### 1. Clone Repository
```bash
git clone https://github.com/javillao/ct-candidates-app.git
cd ct-candidates-app


# 2. Environment Configuration
cp .env.example .env

# 3 Database Configuration (MANDATORY)
DB_DATABASE=todo_list_db
DB_USERNAME=todo_list_user
DB_PASSWORD=System@123

# Email Configuration (MANDATORY for Password Reset)
MAIL_MAILER=smtp
MAIL_HOST=smtp.sendgrid.net
MAIL_PORT=587
MAIL_USERNAME=apikey
MAIL_PASSWORD=your_sendgrid_api_key
MAIL_ENCRYPTION=tls
MAIL_FROM_ADDRESS=grelpitu@gmail.com
MAIL_FROM_NAME="${APP_NAME}"

# 4 Build and Start Containers
docker-compose up -d --build

# PHP dependencies (Laravel)
docker-compose exec laravel.test composer install

# JavaScript dependencies (React)
docker-compose exec node npm install

# 5. Install Dependencies
# Generate application key
docker-compose exec laravel.test php artisan key:generate

# 6. Application Setup
# Run database migrations (AFTER .env configuration)
docker-compose exec laravel.test php artisan migrate


## API Endpoints

### Tasks Management

| Method | Endpoint          | Description                          | Required Headers                                  |
|--------|-------------------|--------------------------------------|---------------------------------------------------|
| GET    | `/api/tasks`      | Get all tasks                        | `Accept: application/json`<br>`Authorization: Bearer <token>` |
| GET    | `/api/tasks/{id}` | Get specific task by ID              | `Accept: application/json`<br>`Authorization: Bearer <token>` |
| POST   | `/api/tasks`      | Create new task                      | `Accept: application/json`<br>`Authorization: Bearer <token>`<br>`Content-Type: application/json` |
| PUT    | `/api/tasks/{id}` | Update existing task                 | `Accept: application/json`<br>`Authorization: Bearer <token>`<br>`Content-Type: application/json` |
| DELETE | `/api/tasks/{id}` | Delete task by ID                    | `Accept: application/json`<br>`Authorization: Bearer <token>` |





