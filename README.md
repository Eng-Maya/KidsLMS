# Kids Learning Arabic API 🎓📚

A RESTful API built with **Laravel** for managing an educational platform for children to learn Arabic. This API handles students, teachers/admins, lessons, quizzes, achievements, and complaints with authentication and role-based access control.

---

## 📖 Table of Contents
- [✨ Features](#-features)
- [🔒 Authentication](#-authentication)
- [👩‍🎓 Student Routes](#-student-routes)
- [👨‍🏫 Teacher/Admin Routes](#-teacheradmin-routes)
- [📘 Lesson Routes](#-lesson-routes)
- [📝 Quiz Routes](#-quiz-routes)
- [📩 Complaint Routes](#-complaint-routes)
- [🏆 Achievements Routes](#-achievements-routes)
- [🛡️ Middleware](#-middleware)
- [🛠️ Tech Stack](#-tech-stack)

---

## ✨ Features
- 🧑‍🎓 Student registration and login  
- 👨‍🏫 Teacher/Admin registration and login  
- 📚 CRUD operations for students, lessons, quizzes  
- 🏆 Track student progress and achievements  
- 📩 Submit and manage complaints  
- 🛡️ Role-based access control  

---

## 🔒 Authentication
- Uses **Laravel Sanctum** for API token authentication  
- Students, teachers, and admins have different access rights  

---

## 👩‍🎓 Student Routes
| Method | Endpoint | Description |
|--------|---------|-------------|
| GET    | `/student/profile` | View student profile |
| GET    | `/student/levels` | View all levels |
| GET    | `/student/lessons/{level_id}` | View lessons for a level |
| GET    | `/student/quizzes/{lesson_id}` | View quizzes for a lesson |
| POST   | `/student/submit-completion` | Submit quiz/game completion |
| POST   | `/student/complaints` | Submit complaints/questions |

---

## 👨‍🏫 Teacher/Admin Routes
| Method | Endpoint | Description |
|--------|---------|-------------|
| POST   | `/admin/add-student` | ➕ Add a new student |
| PUT    | `/admin/update-student/{id}` | ✏️ Update student information |
| DELETE | `/admin/delete-student/{id}` | 🗑️ Soft delete student |
| POST   | `/admin/restore-student/{id}` | ♻️ Restore soft-deleted student |
| GET    | `/admin/students` | 📋 List all students |
| POST   | `/admin/add-teacher` | ➕ Add a teacher |
| PUT    | `/admin/update-teacher/{id}` | ✏️ Update teacher info |
| DELETE | `/admin/delete-teacher/{id}` | 🗑️ Delete a teacher |

---

## 📘 Lesson Routes
| Method | Endpoint | Description |
|--------|---------|-------------|
| POST   | `/admin/add-lesson` | ➕ Create a new lesson |
| PUT    | `/admin/update-lesson/{id}` | ✏️ Update lesson |
| DELETE | `/admin/delete-lesson/{id}` | 🗑️ Delete lesson |
| GET    | `/admin/lessons` | 📋 List all lessons |

---

## 📝 Quiz Routes
| Method | Endpoint | Description |
|--------|---------|-------------|
| POST   | `/admin/add-quiz` | ➕ Create a new quiz |
| PUT    | `/admin/update-quiz/{id}` | ✏️ Update quiz |
| DELETE | `/admin/delete-quiz/{id}` | 🗑️ Delete quiz |
| GET    | `/admin/quizzes` | 📋 List all quizzes |
| GET    | `/admin/student-performance/{student_id}` | 📊 Track student quiz/game performance |

---

## 📩 Complaint Routes
| Method | Endpoint | Description |
|--------|---------|-------------|
| GET    | `/admin/complaints` | 📋 View all complaints |
| GET    | `/admin/complaint/{id}` | 🔍 View complaint by ID |

---

## 🏆 Achievements Routes
| Method | Endpoint | Description |
|--------|---------|-------------|
| PUT    | `/admin/update-points/{student_id}` | ✏️ Update points and achievements |
| GET    | `/student/achievements` | 🏅 View achievements and scores |

---

## 🛡️ Middleware
- `auth:sanctum` → 🔑 Authenticate users  
- `role:student` → 👩‍🎓 Only student access  
- `role:teacher,admin` → 👨‍🏫 Only teacher/admin access  

---

## 🛠️ Tech Stack
- **Backend:** Laravel PHP  
- **Database:** MySQL  
- **Authentication:** Laravel Sanctum  
- **API Type:** RESTful  

---

## 💡 Notes
- Students can access lessons, quizzes, track progress, and submit complaints.  
- Teachers/Admins can manage lessons, quizzes, students, and view reports/complaints.
