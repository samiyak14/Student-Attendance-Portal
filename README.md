# 📚 Student Attendance Portal

A Flask-based student attendance management system designed to simplify attendance recording for teachers while providing a structured interface for managing attendance records.

The application uses **role-based access**, allowing teachers to update attendance records and students to access the portal through a separate login flow.

---

## 📌 Overview

Managing attendance manually can be repetitive and time-consuming. This project explores how a simple web application can streamline the process by allowing teachers to record attendance through an intuitive interface and automatically update existing Excel-based attendance records.

The system provides:

- Teacher and student login roles
- Attendance recording through a web interface
- Excel workbook integration
- Automatic marking of students as Present or Absent
- Date and day tracking
- Session-based authentication
- Flash messages for user feedback

---

## ✨ Features

### 👨‍🏫 Teacher Dashboard

Teachers can:

- Select the attendance workbook and worksheet
- Enter the date and day
- Enter absent student roll numbers
- Submit attendance records
- Automatically update the corresponding Excel sheet

### 👨‍🎓 Student Access

The application provides a separate student role and login flow, forming the foundation for student-facing attendance functionality.

### 📊 Attendance Management

Attendance records are maintained through Excel workbooks using `openpyxl`.

When attendance is submitted:

- Students whose roll numbers are entered as absent are marked **A**
- Remaining students are marked **P**
- The attendance date and day are recorded
- The workbook is saved with the updated attendance information

---

## 🏗️ Application Flow

```text
                ┌──────────────────────┐
                │      Login Page      │
                └──────────┬───────────┘
                           │
              ┌────────────┴────────────┐
              │                         │
              ▼                         ▼
      ┌───────────────┐         ┌───────────────┐
      │ Teacher Login │         │ Student Login │
      └───────┬───────┘         └───────────────┘
              │
              ▼
      ┌───────────────────┐
      │ Teacher Dashboard │
      └─────────┬─────────┘
                │
                ▼
      ┌───────────────────┐
      │ Attendance Input  │
      │                   │
      │ • Workbook        │
      │ • Sheet           │
      │ • Date / Day      │
      │ • Absent Roll Nos │
      └─────────┬─────────┘
                │
                ▼
      ┌───────────────────┐
      │ Excel Workbook    │
      │ Updated with      │
      │ P / A records     │
      └───────────────────┘
```

---

## 🛠️ Technologies Used

- **Python**
- **Flask**
- **HTML**
- **CSS**
- **Jinja2 Templates**
- **openpyxl**
- **Excel / XLSX**
- **Session-based Authentication**

---

## 📂 Project Structure

```text
Student-Attendance-Portal/
│
├── app.py                 # Flask application and backend logic
├── index.html             # Attendance entry interface
├── login.html             # Login page
├── dashboard.html         # Teacher dashboard
├── styles.css             # Application styling
│
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

Make sure you have:

- Python 3.x
- pip

### 1. Clone the repository

```bash
git clone https://github.com/samiyak14/Student-Attendance-Portal.git
cd Student-Attendance-Portal
```

### 2. Install dependencies

Install the required Python packages:

```bash
pip install flask openpyxl
```

Or, if a `requirements.txt` file is added to the project:

```bash
pip install -r requirements.txt
```

### 3. Run the application

Start the Flask application:

```bash
python app.py
```

The application will run locally using Flask's development server.

Open the provided local address in a web browser to access the portal.

---

## 📝 Attendance Workflow

The teacher enters:

1. Workbook name
2. Worksheet name
3. Attendance date
4. Day
5. Roll numbers of absent students

The application then:

1. Opens the specified Excel workbook.
2. Identifies the appropriate attendance column.
3. Matches student roll numbers.
4. Marks students as `A` for absent and `P` for present.
5. Records the date and day.
6. Saves the updated workbook.

---

## 🔐 Authentication

The application uses Flask sessions to maintain login state and distinguish between teacher and student roles.

> **Note:** This project is intended as a study/learning project. The current implementation uses simple in-memory credentials and should not be considered suitable for production deployment without additional security improvements.

For a production implementation, authentication should be moved to a secure database with password hashing, environment-based secrets, proper authorization controls, and secure session configuration.

---

## 🔮 Future Improvements

Potential improvements include:

- Database-backed user management
- Secure password hashing
- Student attendance analytics
- Attendance percentage calculations
- Student-specific dashboards
- Monthly and semester attendance reports
- Improved role-based authorization
- Responsive UI
- Database integration instead of Excel-based storage
- Exportable attendance reports
- Production-ready authentication and security

---

## 📚 Key Learning Outcomes

This project provided practical experience with:

- Building web applications using Flask
- Designing basic role-based application flows
- Handling HTTP requests and form submissions
- Working with HTML, CSS, and Jinja2 templates
- Reading and modifying Excel workbooks programmatically
- Managing sessions and user state
- Connecting a web application to external data files
- Designing a simple automation workflow for a real-world administrative task

---

## 👩‍💻 Author

**Samiya Budye**

Computer Science Engineering — Artificial Intelligence & Machine Learning

[GitHub](https://github.com/samiyak14)
