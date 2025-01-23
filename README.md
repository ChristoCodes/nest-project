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
- Node.js 18+ (optional for local frontend development)

## Getting Started

### 1. Clone Repository
```bash
git clone https://github.com/javillao/ct-candidates-app.git
cd ct-candidates-app

## 2. Environment Configuration
cp .env.example .env

### Edit .env file with these REQUIRED configurations BEFORE running migrations:
# Database Configuration
DB_DATABASE=todo_list_db
DB_USERNAME=todo_list_user
DB_PASSWORD=System@123

# Email Configuration (Mandatory for Password Reset)
MAIL_MAILER=smtp
MAIL_HOST=smtp.sendgrid.net
MAIL_PORT=587
MAIL_USERNAME=apikey
MAIL_PASSWORD=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
MAIL_ENCRYPTION=tls
MAIL_FROM_ADDRESS=grelpitu@gmail.com
MAIL_FROM_NAME="${APP_NAME}"

### 3. Build and Start Services
docker-compose up -d --build

### 4. Install Dependencies 
# Backend dependencies
docker-compose exec laravel.test composer install

# Frontend dependencies
docker-compose exec node npm install


# Generate application key
docker-compose exec laravel.test php artisan key:generate

# Create database structure (RUN AFTER configuring .env)
docker-compose exec laravel.test php artisan migrate
