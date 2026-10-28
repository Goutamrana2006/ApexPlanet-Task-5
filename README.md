<div align="center">

# ✍️ InkSpace
### Blog Management System

**Write. Share. Explore.**

A PHP and MySQL-powered blogging application developed as part of the **ApexPlanet Software Pvt. Ltd. Web Development Internship — Task 5**.

[Features](#-key-features) · [Technology Stack](#-technology-stack) · [Installation](#-installation-and-setup) · [Security](#-security-implementation)

</div>

---

## 📌 Project Overview

**InkSpace** is a database-driven blog management web application that demonstrates practical full-stack web development using PHP, MySQL, HTML5, CSS3, and JavaScript.

The application allows users to register, authenticate, create and manage blog posts, search published content, and navigate posts through pagination.

Developed using XAMPP, InkSpace brings together database integration, authentication, CRUD operations, interface design, and security-conscious coding practices in one project.

### 📋 Project Information

| Detail | Description |
|---|---|
| Project Name | InkSpace — Blog Management System |
| Organization | ApexPlanet Software Pvt. Ltd. |
| Program | Web Development Internship |
| Task | Task 5 |
| Backend | PHP |
| Database | MySQL |
| Frontend | HTML5, CSS3, JavaScript |
| Development Environment | Windows, XAMPP, Visual Studio Code |
| Version Control | Git and GitHub |
| Application Status | Developed for local execution and testing |

---

## 🖥️ Homepage Demo


<img width="1882" height="936" alt="Screenshot 2026-10-29 001015" src="https://github.com/user-attachments/assets/bd21109a-25f7-4ac0-9192-c6afb6120693" />


*The screenshot above is a placeholder reference to the image file expected at `assets/homepage.png`. Add your actual homepage screenshot to display it on GitHub.*

### How to add your homepage screenshot

1. Run Apache and MySQL using the XAMPP Control Panel.
2. Open your application at `http://localhost/ApexPlanet-Task-5/`.
3. Capture a screenshot of the homepage.
4. Create an `assets` folder in your project root.
5. Save the screenshot as `homepage.png` inside that folder.
6. Commit and push the screenshot to GitHub.

**Note:** The local URL is for development on your computer; it is not a publicly hosted demo.

---

## ✨ Key Features

### 🔐 User Authentication
- User registration and login.
- Password hashing with PHP's `password_hash()`.
- Password verification using `password_verify()`.
- Session-based authentication.
- Session ID regeneration after successful login.
- Logout functionality.

### 📝 Blog Management
- Create blog posts with titles and content.
- Explore published posts.
- Edit existing posts.
- Delete posts through POST requests.
- Display article content and publication dates.
- Validate submitted post information.

### 🔎 Search and Navigation
- Search posts by title or content.
- Navigate posts using pagination.
- Handle empty search results.
- Validate pagination input.

### 🎨 User Interface
- Consistent styling across application pages.
- Dedicated styling for article creation and editing.
- Responsive layouts for supported screen sizes.
- Success and error feedback for supported operations.
- Confirmation before deleting a post.
- Automatically dismissible notifications.

### 🛡️ Security-Oriented Development
- Prepared SQL statements.
- HTML output escaping.
- CSRF token generation and validation.
- Authentication checks for protected pages.
- Server-side input validation.
- Session management and logout handling.

*Feature descriptions reflect the intended implementation. Verify each feature in the current application before treating it as fully tested.*

---

## 🧰 Technology Stack

| Technology | Purpose |
|---|---|
| HTML5 | Page structure and forms |
| CSS3 | Layout, styling, and responsive design |
| JavaScript | Interactive behavior and notification dismissal |
| PHP | Server-side processing and application logic |
| MySQL | Persistent storage for users and blog posts |
| Apache | Local web server |
| XAMPP | Local PHP and MySQL development environment |
| Visual Studio Code | Code editing and debugging |
| Git | Version control |
| GitHub | Source code hosting and project collaboration |

---

## 📁 Project Structure

```text
ApexPlanet-Task-5/
│
├── assets/
│   └── homepage.png
│
├── auth/
│   ├── login.php
│   ├── logout.php
│   └── register.php
│
├── config/
│   └── database.php
│
├── posts/
│   ├── index.php
│   ├── create.php
│   ├── edit.php
│   ├── delete.php
│   ├── posts.css
│   ├── editor.css
│   └── edit.css
│
├── .gitignore
├── index.php
├── style.css
├── home.css
└── README.md
```

The `assets/homepage.png` file is intended for the homepage screenshot. Add it to the project when the screenshot is ready.

---

## ⚙️ Requirements

Before running InkSpace, ensure that you have:

- Windows, Linux, or macOS.
- XAMPP with Apache, PHP, and MySQL/MariaDB.
- A modern web browser.
- Visual Studio Code or another code editor.
- Git, if cloning the repository through the terminal.

---

## 🚀 Installation and Setup

Follow these steps to run InkSpace locally.

### 1. Clone the repository

```bash
git clone https://github.com/Goutamrana2006/ApexPlanet-Task-5.git
```

Navigate into the project directory:

```bash
cd ApexPlanet-Task-5
```

### 2. Move the project into XAMPP

For a standard Windows XAMPP installation, place the project inside:

```text
C:\xampp\htdocs\ApexPlanet-Task-5
```

Ensure that `index.php`, `auth/`, `config/`, and `posts/` are present.

### 3. Start Apache and MySQL

1. Open the XAMPP Control Panel.
2. Start **Apache**.
3. Start **MySQL**.
4. Confirm that both services are running.

### 4. Create the database

Open phpMyAdmin:

```text
http://localhost/phpmyadmin/
```

Create a database named:

```text
blog
```

Create the required `users` and `posts` tables using the schema expected by your application.

**Important:** The exact database schema must match the SQL queries in your current PHP files. If you already have a working database, verify its schema before making changes.

### 5. Configure the database connection

Open:

```text
config/database.php
```

Configure the host, username, password, and database name to match your local MySQL installation.

Typical local XAMPP settings may use:

```text
Host: localhost
Username: root
Database: blog
Password: Your configured MySQL password
```

A blank password is appropriate only if that is how your local MySQL account is configured.

**Never commit real passwords, API keys, or other private credentials to GitHub.**

### 6. Run InkSpace

Open the application in your browser:

```text
http://localhost/ApexPlanet-Task-5/
```

Register an account, log in, and explore the available blog-management features.

---

## 🗄️ Database Overview

The application uses MySQL for persistent data storage.

### Users Table

The application references the following user information:

| Field | Purpose |
|---|---|
| `id` | Unique user identifier |
| `username` | Username used for registration and login |
| `password` | Stored password hash |

Recommended database constraints include a primary key on `id` and a unique constraint on `username`.

### Posts Table

The application references the following post information:

| Field | Purpose |
|---|---|
| `id` | Unique post identifier |
| `title` | Blog post title |
| `content` | Blog post content |
| `created_at` | Post creation timestamp |

The exact column types, indexes, relationships, and additional fields should be verified against the database schema used by your current project.

If posts are intended to belong to individual users, the database and all post operations must consistently enforce that ownership relationship.

---

## 🔒 Security Implementation

InkSpace incorporates several security-oriented programming practices.

| Security Measure | Implementation |
|---|---|
| Password security | `password_hash()` and `password_verify()` |
| SQL injection prevention | Prepared statements for queries involving user input |
| Cross-site scripting protection | HTML output escaping with `htmlspecialchars()` |
| CSRF protection | Random tokens and validation using `hash_equals()` |
| Session security | Session ID regeneration after successful login |
| Authentication | Session checks for protected pages |
| Input validation | Server-side validation of submitted values |
| Post deletion | POST requests with appropriate validation |
| Error handling | Avoid exposing internal database errors directly to users |

### Security Considerations

Security depends on how these controls are implemented across the entire application.

Before submission, verify that:
- Every protected operation checks authentication.
- Users cannot modify posts belonging to other users when ownership restrictions apply.
- All relevant state-changing forms validate CSRF tokens.
- User-generated content is escaped appropriately.
- Database credentials remain private.
- Logout invalidates the authenticated session.
- Invalid input and unexpected database errors are handled safely.

These measures reduce common risks but do not guarantee that the application is vulnerability-free.

---

## 🧪 Testing Checklist

Use this checklist to track your final verification.

### Authentication
- [ ] Register a new user.
- [ ] Attempt to register an existing username.
- [ ] Log in with valid credentials.
- [ ] Verify that invalid credentials are rejected.
- [ ] Verify that protected pages require authentication.
- [ ] Log out and confirm that the session is no longer authenticated.

### Blog Management
- [ ] Create a post.
- [ ] Confirm that the post appears in the listing.
- [ ] Edit a post and verify the changes.
- [ ] Delete a post and confirm that it is removed.
- [ ] Verify handling of invalid post IDs.
- [ ] Test post ownership restrictions, if applicable.

### Search and Pagination
- [ ] Search by title.
- [ ] Search by content.
- [ ] Test a search with no matching results.
- [ ] Navigate between pages.
- [ ] Test invalid or out-of-range page values.

### Security and Interface
- [ ] Confirm that passwords are stored as hashes.
- [ ] Test CSRF validation on protected operations.
- [ ] Check output escaping for user-generated content.
- [ ] Verify prepared statements.
- [ ] Test success and error notifications.
- [ ] Check automatic notification dismissal.
- [ ] Test the interface at desktop and mobile widths.
- [ ] Verify the installation instructions using the expected database schema.

Mark each item complete only after testing it.

---

## 📈 Development Progress: Tasks 1–5

### Task 1 — Git and GitHub Setup
- Repository and version control setup.
- Initial project file management.
- Practice with commits and pushes.

### Task 2 — Authentication and CRUD Operations
- User registration and login.
- Password hashing and verification.
- PHP and MySQL integration.
- Blog post creation, listing, editing, and deletion.

### Task 3 — Search, Pagination, and UI Improvements
- Search by post title and content.
- Pagination and result navigation.
- Layout and styling improvements.
- Empty-result handling.

### Task 4 — Security Enhancements
- Authentication checks.
- Session ID regeneration.
- CSRF token handling.
- Prepared statements and output escaping.
- Validation of post operations.

### Task 5 — UI Refinement and Finalization
- Refined article editor and dashboard styling.
- Improved user feedback and notifications.
- Continued testing of post-management workflows.
- Documentation and final project preparation.

The progress descriptions summarize the intended development stages. Completion of individual requirements should be based on the actual implementation and testing results.

---

## 🎓 Learning Outcomes

Developing InkSpace provided practical experience with:

- HTML, CSS, and JavaScript.
- Server-side programming with PHP.
- Database integration using MySQL.
- CRUD operations.
- Form processing and input validation.
- Password hashing and session management.
- Prepared SQL statements.
- CSRF protection and output escaping.
- Debugging with XAMPP.
- Version control using Git and GitHub.
- UI refinement and technical documentation.

---

## 🔮 Future Improvements

Potential enhancements include:

- Dedicated article details pages.
- A personal article dashboard.
- Author profiles and accurate author attribution.
- Categories and tags.
- Comments and likes.
- Password recovery.
- Additional accessibility improvements.
- Further responsive-design refinements.

These are potential future enhancements, not claims about existing functionality.

---

## 🏢 Internship Information

**Organization:** ApexPlanet Software Pvt. Ltd.  
**Program:** Web Development Internship  
**Project:** InkSpace — Blog Management System  
**Task:** Task 5  
**Technology Stack:** PHP, MySQL, HTML5, CSS3, JavaScript  
**Development Tools:** XAMPP, Visual Studio Code, Git, GitHub

This project was developed for educational purposes as part of the ApexPlanet Web Development Internship.

---

## 🙏 Acknowledgment

Thank you to **ApexPlanet Software Pvt. Ltd.** for the opportunity to gain practical web development experience through hands-on internship tasks.

---

<div align="center">

**InkSpace — Write. Share. Explore.**

*Built with PHP, MySQL, HTML, CSS, and JavaScript.*

</div>
