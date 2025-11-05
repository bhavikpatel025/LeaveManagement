🚀 Leave Management System - Full Stack Application

A complete leave management solution built with .NET Core Web API backend and Angular 19 frontend. This enterprise-grade system provides comprehensive leave management functionality with role-based authorization and modern UI.

📋 Table of Contents
Features

Technologies Used
Installation
Usage
API Endpoints
Database Schema
Authentication
Project Structure
Frontend Details
Configuration
Contributing

✨ Features
🔐 Authentication & Authorization

JWT-based secure authentication
Role-based access control (Admin/Employee)
Password hashing with bcrypt
Token expiration handling

👥 User Management

Employee registration with role assignment
User profile management
Leave balance initialization
Admin user management

📅 Leave Management

Apply for leave requests
Leave approval/rejection workflow
Leave cancellation (with business rules)
Leave history tracking
Leave balance management

📊 Admin Features

Employee registration and management
Leave request approval system
Leave reports and filtering
Excel export functionality
Dashboard metrics and analytics

🎨 Frontend Features

Responsive Angular 19 UI
Modern Angular Material Design
Real-time data updates
Mobile-friendly interface
Interactive charts and dashboards

🛡️ Security & Validation

Input validation and sanitization
CORS configuration
Secure password handling
Data transfer objects (DTOs)
Authorization filters

🛠️ Technologies Used

Backend
Framework: .NET 8.0 / ASP.NET Core Web API
Database: SQL Server with Entity Framework Core
Authentication: JWT (JSON Web Tokens)
ORM: Entity Framework Core (Code First)
Mapping: AutoMapper
Architecture: Repository Pattern with Dependency Injection
Documentation: Swagger/OpenAPI
Testing: xUnit (ready for implementation)

Frontend
Framework: Angular 19
UI Library: Angular Material
State Management: RxJS
HTTP Client: Angular HttpClient
Routing: Angular Router with Guards
Forms: Reactive Forms
Icons: Angular Material Icons

📦 Installation

Prerequisites
.NET 8.0 SDK or later

Node.js 18+ and npm

SQL Server (LocalDB or full version)

Angular CLI: npm install -g @angular/cli

Visual Studio 2022 or VS Code

Backend Setup
Navigate to backend directory

bash
cd LeaveManagement.API
Restore NuGet packages

bash
dotnet restore
Update database connection string
Edit appsettings.json:

json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=LeaveManagementDB;Trusted_Connection=true;"
  }
}
Create and migrate database

bash
dotnet ef migrations add InitialCreate
dotnet ef database update
Run the backend application

bash
dotnet run
Backend will be available at: https://localhost:7000

Frontend Setup
Navigate to frontend directory

bash
cd leave-management-frontend
Install dependencies

bash
npm install
Configure API URL
Update src/environments/environment.ts:

typescript
export const environment = {
  production: false,
  apiUrl: 'https://localhost:7000/api'
};
Run the frontend application

bash
ng serve
Frontend will be available at: http://localhost:4200

🚀 Quick Start

bash
# Clone the repository
git clone https://github.com/bhavikpatel025/LeaveManagement.git
cd LeaveManagement

# Backend setup
cd LeaveManagement.API
dotnet restore
dotnet ef database update
dotnet run

# Frontend setup (new terminal)
cd leave-management-frontend
npm install
ng serve

📚 API Endpoints
Authentication

Method	Endpoint	Description	Auth Required
POST	/api/auth/login	User login	❌
POST	/api/auth/register	Register employee	✅ Admin
Users Management
Method	Endpoint	Description	Auth Required
GET	/api/users	Get all employees	✅ Admin
GET	/api/users/{id}	Get employee by ID	✅
PUT	/api/users/{id}/leave-balance	Update leave balance	✅ Admin
Leave Management
Method	Endpoint	Description	Auth Required
POST	/api/leaves/apply	Apply for leave	✅ Employee
GET	/api/leaves/my-leaves	Get personal leaves	✅ Employee
GET	/api/leaves/all	Get all leave requests	✅ Admin
PUT	/api/leaves/{id}/cancel	Cancel leave request	✅ Employee
PUT	/api/leaves/update-status	Approve/reject leave	✅ Admin
GET	/api/leaves/types	Get leave types	✅
GET	/api/leaves/export	Export leaves to Excel	✅ Admin

Leave Types:
Annual Leave
Sick Leave
Personal Leave
Maternity/Paternity Leave

🔐 Authentication

JWT Configuration
json
{
  "JwtSettings": {
    "Key": "your-super-secret-jwt-signing-key-here",
    "Issuer": "LeaveManagementAPI",
    "Audience": "LeaveManagementClient",
    "ExpiryInHours": 24
  }
}

Authorization Levels
Employee: Can apply for leaves, view own leaves, cancel own leaves
Admin: Full access to all endpoints, user management, leave approvals

🎨 Frontend Details
Angular 19 Features:

Standalone Components - Modern Angular architecture
Reactive Forms - Robust form handling with validation
RxJS Observables - Efficient state management
Angular Material - Professional UI components
Route Guards - Protected routes based on user roles
HTTP Interceptors - Automatic token handling

Key Frontend Components:

Login/Register - Authentication pages
Dashboard - Overview for employees and admins
Leave Application - Form to apply for leave
Leave History - Personal leave records
Admin Panel - User and leave management
Reports - Analytics and export functionality

🧪 Testing

Backend Testing
bash
# Create test project
dotnet new xunit -n LeaveManagementAPI.Tests

# Add test dependencies
dotnet add package Microsoft.EntityFrameworkCore.InMemory
dotnet add package Moq
Frontend Testing
bash
# Run unit tests
ng test

# Run e2e tests
ng e2e

# Run with coverage
ng test --code-coverage
Manual Testing
Use Swagger UI at /swagger for API testing
Test frontend functionality in browser
Verify authentication flows
Test role-based access control

# Backend
cd LeaveManagement.API
dotnet publish -c Release -o ./publish

# Frontend
cd leave-management-frontend
ng build --configuration production

🤝 Contributing

Fork the repository
Create a feature branch (git checkout -b feature/amazing-feature)
Commit your changes (git commit -m 'Add amazing feature')
Push to the branch (git push origin feature/amazing-feature)
Open a Pull Request

Development Guidelines
Follow C# coding conventions for backend
Follow Angular style guide for frontend
Write unit tests for new features
Update API documentation
Ensure all migrations are included

📝 License
This project is licensed under the MIT License - see the LICENSE file for details.

🙏 Acknowledgments

Microsoft for .NET Core and Entity Framework
Angular Team for the amazing frontend framework
JWT.io for JWT implementation guidance
Swagger for API documentation
AutoMapper for object-to-object mapping

📞 Contact

Developer: Bhavik Patel
Email: pb3721700@gmail.com
LinkedIn: https://www.linkedin.com/in/bhavik-patel-217a402a5/
