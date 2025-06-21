# Project Evaluation System

A Django-based web application for managing student project submissions and teacher evaluations.

## Features

### Student Features:
- Student registration with name, email, roll number, and 6-digit password
- Course enrollment using teacher-provided course codes
- View enrolled courses and assignments
- Upload project files for assignments
- View evaluation marks and feedback from teachers
- Track evaluation status and see how many teachers have evaluated

### Teacher Features:
- Teacher registration with name, email, department, and 6-digit password
- Create courses with auto-generated course codes
- Manage student enrollments (view and remove students)
- Create assignments with descriptions and maximum marks
- View all student submissions for assignments
- Evaluate submissions with marks and feedback
- Dashboard with evaluation statistics

### Homepage:
- Welcome page with system overview
- Easy navigation to login and registration
- Feature highlights

## Tech Stack

- **Backend**: Django 5.2.3
- **Database**: SQLite (built-in)
- **Frontend**: HTML templates with CSS
- **File Uploads**: Django's file handling system

## Installation and Setup

### Prerequisites
- Python 3.11+
- Django 5.2.3
- Pillow (for file handling)

### Running the Project

1. **Install Dependencies** (already done in Replit):
   ```bash
   pip install django pillow
   ```

2. **Database Setup** (already done):
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

3. **Create Superuser** (already done):
   ```bash
   python manage.py createsuperuser
   # Username: admin
   # Email: admin@example.com
   # Password: 123456
   ```

4. **Run the Server**:
   ```bash
   python manage.py runserver 0.0.0.0:8000
   ```

5. **Access the Application**:
   - Homepage: http://localhost:8000/
   - Admin Panel: http://localhost:8000/admin/
   - Student/Teacher Registration: http://localhost:8000/accounts/register/

## Project Structure

```
project_evaluation/
├── project_evaluation/          # Main Django project
│   ├── settings.py             # Project settings
│   ├── urls.py                 # Main URL configuration
│   └── wsgi.py                 # WSGI configuration
├── accounts/                   # User authentication app
│   ├── models.py              # Custom user model
│   ├── views.py               # Authentication views
│   └── urls.py                # Account URLs
├── courses/                    # Course management app
│   ├── models.py              # Course, Assignment, Enrollment models
│   ├── views.py               # Course management views
│   └── urls.py                # Course URLs
├── evaluations/                # Evaluation system app
│   ├── models.py              # Submission, Evaluation models
│   ├── views.py               # Evaluation views
│   └── urls.py                # Evaluation URLs
├── templates/                  # HTML templates
│   ├── base.html              # Base template
│   ├── home.html              # Homepage
│   ├── accounts/              # Authentication templates
│   ├── courses/               # Course templates
│   └── evaluations/           # Evaluation templates
├── static/css/                 # CSS styles
│   └── style.css              # Main stylesheet
└── media/                      # User uploaded files
    └── submissions/            # Student submissions
```

## Usage Guide

### For Students:

1. **Register**: Go to registration page and select "Student"
2. **Login**: Use your email and 6-digit password
3. **Enroll**: Use course codes provided by teachers to join courses
4. **Submit**: Upload project files for assignments
5. **View Results**: Check your submissions and teacher evaluations

### For Teachers:

1. **Register**: Go to registration page and select "Teacher"
2. **Login**: Use your email and 6-digit password
3. **Create Course**: Set up new courses (course codes auto-generated)
4. **Manage Students**: View enrolled students and remove if needed
5. **Create Assignments**: Add assignments with descriptions and max marks
6. **Evaluate**: Review student submissions and provide marks/feedback

### Admin Features:

- Access admin panel at `/admin/`
- Manage all users, courses, assignments, and evaluations
- View system statistics and data

## Security Features

- User authentication required for all operations
- Role-based access control (student vs teacher)
- File upload validation
- CSRF protection on all forms
- SQL injection protection via Django ORM

## File Upload System

- Students can upload any file type for assignments
- Files are stored in `media/submissions/` directory
- Teachers can download and review submitted files
- File names are preserved for easy identification

## Database Schema

- **CustomUser**: Extended Django user with role, roll_number, department
- **Course**: Course information with auto-generated codes
- **Enrollment**: Student-course relationships
- **Assignment**: Course assignments with descriptions and marks
- **Submission**: Student file uploads for assignments
- **Evaluation**: Teacher evaluations with marks and feedback

## Customization

The system can be easily extended with:
- Additional user fields
- File type restrictions
- Email notifications
- Advanced evaluation criteria
- Reporting and analytics
- Mobile responsiveness improvements

## Support

For issues or questions about the system, check the Django documentation or contact the system administrator.