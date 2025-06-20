# Attendance Management System - Django Application

This Django-based web application is designed for managing and recording student attendance. It supports role-based access for faculty and students, providing tailored dashboards and functionalities to each user type.

---

## Features

### Authentication
- Secure login/logout using Django's authentication system
- Role-based redirection (Faculty, Student)

### Faculty Functionalities
- Take attendance for a class by selecting subject and period
- Record and update student attendance with date and present/absent status
- View attendance dashboard with visual data on student attendance
- Edit personal profile information
- Change password

### Student Functionalities
- View personal attendance statistics (present, absent days)
- Profile update functionality
- Change password securely

### Reports
- Generate and download attendance reports as CSV
- Filter reports by faculty, student, and date

---

## Setup Instructions

### Requirements
- Python >= 3.8
- Django >= 3.2
- SQLite (default) or any configured DB

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/Mangaleshwaran2002/Attendance
   cd Attendance
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run migrations:
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```
4. Create a superuser:
   ```bash
   python manage.py createsuperuser
   ```
5. Start the development server:
   ```bash
   python manage.py runserver
   ```

---

## Project Structure

- `app_auth/`: Handles login, logout, redirection, and user roles
- `faculty/`: Faculty-specific views and attendance recording
- `student/`: Student-specific views and profile management
- `records/`: Models for attendance, subjects, periods; reporting features
- `templates/`: Contains all HTML templates for each module

---

## Models

### `Subjects`
- Related to `Department`
- Holds subject name

### `Attendance`
- Linked with `Student`, `Faculty`, and `Subjects`
- Stores date, period, present status

### `Period`
- Enum for period choices (FIRST to SEVENTH)

---

## Security and Best Practices
- Decorated all views with `@login_required`
- Used Django `messages` for user notifications
- Password change includes confirmation check
- Role-based access control

---

## Future Improvements
- Add pagination to report view
- Export in Excel/PDF format
- API integration for mobile or frontend

---

## License
MIT License

---

## Author
Developed by Mangalesh.
