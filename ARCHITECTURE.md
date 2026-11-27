Student Task and Assignment Tracker

1. Project Overview

The Student Task and Assignment Tracker is a web application designed to help students organize their academic assignments and track their deadlines.
Students can register, log in, add assignments, view their tasks, update assignment status, and delete completed or unnecessary tasks.

2. Objectives

- Organize academic assignments in one place.
- Track assignment deadlines.
- Monitor pending and completed tasks.
- Provide a simple and user-friendly interface.

3. Technology Stack

| Layer           | Technology            |
| --------------- | --------------------- |
| Frontend        | HTML, CSS, JavaScript |
| Backend         | Python Flask          |
| Database        | MySQL                 |
| API             | REST API              |
| Version Control | Git and GitHub        |

4. System Architecture

The application contains three main layers:

1. Frontend: Displays web pages and collects user input.
2. Backend: Flask handles requests, validates data, and performs application logic.
3. Database: MySQL stores user and assignment information.

 Application Flow
 Student → Frontend → Flask REST API → MySQL Database → Backend Response → Frontend Display

5. Database Design

Users Table

| Field         | Data Type                        | Description              |
| ------------- | -------------------------------- | ------------------------ |
| user_id       | INT, Primary Key, AUTO_INCREMENT | Unique user ID           |
| name          | VARCHAR(100)                     | Student name             |
| email         | VARCHAR(150), UNIQUE             | Student email            |
| password_hash | VARCHAR(255)                     | Securely hashed password |
| created_at    | DATETIME                         | Account creation date    |

Assignments Table

| Field         | Data Type                        | Description              |
| ------------- | -------------------------------- | ------------------------ |
| assignment_id | INT, Primary Key, AUTO_INCREMENT | Unique assignment ID     |
| user_id       | INT, Foreign Key                 | Reference to Users table |
| title         | VARCHAR(150)                     | Assignment title         |
| description   | TEXT                             | Assignment details       |
| due_date      | DATE                             | Submission deadline      |
| status        | VARCHAR(30)                      | Pending or Completed     |
| created_at    | DATETIME                         | Creation date            |

Relationship:

One student can have multiple assignments. Each assignment belongs to one student.

- Users.user_id → Assignments.user_id
- Relationship: One-to-Many (1:N)

6. API Design

| Method | Endpoint                | Purpose                  |
| ------ | ----------------------- | ------------------------ |
| POST   |  /api/register          | Register a student       |
| POST   |  /api/login             | Authenticate a student   |
| GET    |  /api/assignments       | View student assignments |
| POST   |  /api/assignments       | Add a new assignment     |
| GET    |  /api/assignments/{id}  | View one assignment      |
| PUT    |  /api/assignments/{id}  | Update an assignment     |
| DELETE |  /api/assignments/{id}  | Delete an assignment     |

7. Frontend Screens

1. Registration Page: New students can create an account.
2. Login Page: Registered students can log in.
3. Dashboard: Displays assignment summaries.
4. Add Assignment Page: Allows students to add assignment details.
5. Assignment List Page: Displays assignments with their deadlines and status.
6. Edit Assignment Page: Allows students to update assignment details.

8. Project Folder Structure
SWYNEX-Student-Task-Tracker/
│
├── app.py
├── requirements.txt
├── config.py
│
├── templates/
│   ├── login.html
│   ├── register.html
│   ├── dashboard.html
│   └── assignments.html
│
├── static/
│   ├── css/
│   │   └── style.css
│   └── js/
│       └── script.js
│
├── database/
│   └── schema.sql
│
└── README.md


9. Security and Validation

- Store passwords using secure password hashing.
- Validate user inputs before saving data.
- Use parameterized database queries.
- Allow students to access only their own assignments.
- Handle invalid requests and errors appropriately.

10. Future Enhancements

- Email reminders for upcoming deadlines.
- Assignment priority levels.
- Calendar view.
- Progress reports.
- Mobile-friendly interface.

11. Conclusion

The Student Task and Assignment Tracker aims to make academic task management easier for students. The proposed architecture separates the frontend, backend, and database, making the application easier to maintain and expand.

Project Status:Architecture Planning – SWYNEX Internship Task 1.


