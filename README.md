# Course Management Platform

## Project Overview
The Course Management Platform is a robust and scalable full-stack solution designed to streamline educational operations. It is tailored to manage students, teachers, classrooms, lesson scheduling, and financial tracking effectively. The platform is built to ensure data integrity, security, and maintainability, making it ideal for institutions that require efficient course and financial management.

This project demonstrates a modular design with an emphasis on real-world use cases such as scheduling conflict prevention, detailed user roles, and comprehensive financial tracking through a dedicated accounting system. While the full source code is proprietary, this repository provides an overview of the architecture, core functionalities, and the technologies used.

## Features

### 1. User Management
- **Authentication and Authorization**: 
  - Implements JWT-based authentication for secure user access.
  - Role-based access control ensures that only authorized users can perform specific actions.
- **User Roles**: 
  - Roles include administrators and secretaries, each with defined permissions.
  - Administrators have full access, while secretaries manage day-to-day operations.

### 2. Student Management
- **Comprehensive Profiles**:
  - Maintain detailed student records including personal information, contact details, and academic data.
- **Enrollment Information**:
  - Track enrolled courses, assigned packages, and financial details such as tuition fees and payment installments.
- **CRUD Operations**:
  - Add, update, view, and delete student records via API endpoints.

### 3. Teacher Management
- **Detailed Records**:
  - Manage teacher profiles with fields such as name, branch, and unique identifiers (TC Kimlik No).
- **Validation**:
  - TC Kimlik No is validated to ensure it is unique, numeric, and 11 characters long.
- **Association**:
  - Teachers are linked to lessons for accurate scheduling and accountability.

### 4. Classroom Management
- **Classroom Inventory**:
  - Maintain a list of available classrooms and their details.
- **Conflict Prevention**:
  - Ensure classrooms are not double-booked using scheduling validation.
- **Relationships**:
  - Classrooms are directly associated with lessons to simplify allocation.

### 5. Lesson Scheduling
- **Conflict Resolution**:
  - Prevent scheduling conflicts with real-time validation for overlapping times.
- **Detailed Scheduling**:
  - Specify lesson start and end times, assigned teacher, classroom, and pricing.
- **Financial Integration**:
  - Each scheduled lesson automatically logs a financial transaction in the accounting system.

### 6. Financial Tracking
- **Kasa System**:
  - Dedicated module for managing income and expenses.
  - Supports logging financial transactions with descriptions, amounts, and dates.
- **Integration with Lessons**:
  - Automatically logs lesson-related transactions, ensuring accurate financial records.
- **CRUD Operations**:
  - Add, update, view, and delete financial entries.

### 7. Validation and Constraints
- **Strict Validation**:
  - Validation at both API and database levels ensures data integrity.
- **Defined Constraints**:
  - Includes unique identifiers and allowable values for specific fields (e.g., lesson rental types).

## Project Structure
The project follows a modular and organized structure, ensuring scalability and maintainability:

```
course-management-platform/
│
├── README.md
├── .gitignore
├── backend/
│   ├── app.js
│   ├── config/
│   │   ├── config.js
│   ├── controllers/
│   │   ├── classroomController.js
│   │   ├── dersController.js
│   │   ├── kasaController.js
│   │   ├── ogretmenController.js
│   │   ├── studentController.js
│   │   └── authController.js
│   ├── middleware/
│   │   ├── authMiddleware.js
│   ├── migrations/
│   │   ├── 20241001131936-create-users-table.js
│   │   ├── 20241001132813-seed-users.js
│   │   └── 20241003095645-update-kiralama-turu-constraint.js
│   ├── models/
│   │   ├── Classroom.js
│   │   ├── Ders.js
│   │   ├── Kasa.js
│   │   ├── Ogretmen.js
│   │   ├── Ogrenci.js
│   │   └── User.js
│   ├── routes/
│   │   ├── classroomRoutes.js
│   │   ├── dersRoutes.js
│   │   ├── kasaRoutes.js
│   │   ├── lessonRoutes.js
│   │   ├── ogretmenRoutes.js
│   │   ├── studentRoutes.js
│   │   └── authRoutes.js
│   ├── utils/
│   │   ├── generate_password_hashes.js
│   ├── .env.example
│   ├── package.json
│   └── README.md (Optional for the backend)
├── frontend/
│   ├── html/
│   │   ├── dersler.html
│   │   ├── dersEkle.html
│   │   ├── guvenlik.html
│   │   ├── index.html
│   │   ├── kasa.html
│   │   ├── kutuphane.html
│   │   ├── ogrenci_islem.html
│   │   ├── ogrenci_listesi.html
│   │   ├── ogretmenler.html
│   │   ├── ozelders.html
│   │   ├── paketler.html
│   │   ├── profil.html
│   │   ├── salon.html
│   │   └── salonekle.html
│   ├── styles/
│   │   ├── main.css
│   │   ├── responsive.css
│   ├── scripts/
│   │   ├── app.js
│   │   ├── formHandlers.js
│   └── assets/
│       ├── images/
│       └── icons/
```

## Technology Stack
- **Backend**: 
  - Node.js with Express.js for server-side development.
- **Frontend**:
  - HTML5, CSS3, Bootstrap for responsive design.
  - Vanilla JavaScript for dynamic functionality.
- **Database**: 
  - PostgreSQL managed with Sequelize ORM.
- **Security**:
  - bcrypt for password hashing and JWT for secure authentication.
- **Validation**:
  - Middleware for input validation and role-based access control.

## Deployment
The platform was deployed using a robust and scalable deployment pipeline:

1. **Docker**:
   - The application was containerized using Docker, enabling consistent environments across development and production.
   - Docker Compose was used to manage multi-container setups, including the application and database.

2. **VPS Hosting**:
   - The application was deployed on a Virtual Private Server (VPS) for better control and scalability.

3. **Reverse Proxy**:
   - Nginx was configured as a reverse proxy to handle incoming requests and route them to the Node.js application.

4. **Process Manager**:
   - PM2 was used to ensure the application runs persistently and can automatically recover from crashes.

5. **Database**:
   - PostgreSQL was set up with proper security measures and managed using Sequelize ORM for database migrations and models.

## Screenshots
- Add screenshots from the application to showcase the user interface and functionality.

## Disclaimer
This repository serves as a showcase for the project and includes only non-sensitive information. The full codebase is proprietary and not available for public access.

