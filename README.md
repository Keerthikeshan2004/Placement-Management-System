# 🎓 Placement Management System

A web-based Student Management System built with **Django** and **SQLite**. It lets you manage students, courses, and teachers from a clean dashboard, with add, view, update, and delete operations for student records.

## ✨ Features

- 📊 **Dashboard**: live counts of total students, teachers, and courses
- 👨‍🎓 **Student management**: add, view, search by roll number, update, and delete students
- 📚 **Course management**: add courses and view the course list
- 👩‍🏫 **Teacher listing**: view all teachers and their subject specializations
- 🔗 **Relational data**: each student is linked to a course, and each course to a teacher
- ✅ **Duplicate protection**: roll numbers, emails, and course codes must be unique
- 🔐 **Django Admin panel** with list display, search, and filters for all models

## 🗂️ Data Models

| Model | Fields |
|-------|--------|
| **Teacher** | `teacher_name`, `subject_specialization`, `teacher_email` (unique) |
| **Courses** | `course_name`, `course_code` (unique), `teacher` (FK → Teacher) |
| **Students** | `name`, `roll_number` (unique), `email` (unique), `date_of_birth`, `course` (FK → Courses) |

## 🛠️ Tech Stack

- **Backend:** Python, Django
- **Database:** SQLite
- **Frontend:** HTML, CSS, Django Templates, Font Awesome

## 📁 Project Structure

```
Student_Management_System/
├── manage.py
├── db.sqlite3
├── Student/                      # Main app
│   ├── models.py                 # Teacher, Courses, Students
│   ├── views.py                  # Application logic
│   ├── admin.py                  # Admin configuration
│   ├── migrations/
│   └── templates/                # HTML templates
└── Student_Management_System/    # Project settings & URLs
```

## 🚀 Getting Started

### Prerequisites
- Python 3.10+
- pip

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/Student_Management_System.git
cd Student_Management_System

# 2. (Optional) Create a virtual environment
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

# 3. Install Django
pip install django

# 4. Apply migrations
python manage.py migrate

# 5. (Optional) Create an admin user
python manage.py createsuperuser

# 6. Run the server
python manage.py runserver
```

Open **http://127.0.0.1:8000/** in your browser.

## 🔗 URL Routes

| URL | Description |
|-----|-------------|
| `/` or `/home` | Dashboard |
| `/students_list` | View all students |
| `/addStudent` | Add a new student |
| `/studentDetails` | Search a student by roll number |
| `/Update_form?id=<roll_no>` | Update a student |
| `/Delete?id=<roll_no>` | Delete a student |
| `/course_list` | View all courses |
| `/addCourse` | Add a new course |
| `/teacher_list` | View all teachers |
| `/admin` | Django admin panel |

## 🔮 Future Improvements

- Add teacher add/edit/delete pages
- Edit and delete for courses
- Authentication and role-based access
- Pagination and search on list pages
- Replace manual roll-number checks with Django form validation

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
