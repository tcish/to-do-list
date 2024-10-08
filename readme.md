# Project Name: Task Management

## Introduction

It's a to-do list task management project, which aimed to help users organize and manage tasks efficiently.

---

## Prerequisites

Before starting, ensure the following software is installed on your system:

- [PHP >= 8.2](https://www.php.net/downloads)
- [Composer](https://getcomposer.org/download/)
- [Node.js & npm](https://nodejs.org/en/)
- [Git](https://git-scm.com/)
- [MySQL (or any supported database)](https://www.mysql.com/downloads/)

---

## Installation

**Clone the Repository**

First, clone the project repository from GitHub using the following command:

```bash
git clone https://github.com/tcish/to-do-list.git
```

**Navigate into the project directory:**
```bash
cd to-do-list
```

**Install dependencies:**
```bash
composer i
npm i
```

**Copy the .env.example file to create your .env configuration file:**
```bash
cp .env.example .env
```

**Open the .env file and add database name**
- DB_DATABASE=your_database_name

**Generate an application key:**
```bash
php artisan key:generate
```

**Migrate the database:**
```bash
php artisan migrate
```

**Seed the database to add admin user:**
```bash
php artisan db:seed --class=AdminUserSeeder
```

**Build local frontend assets:**
```bash
npm run dev
```

**Start the Laravel development server:**
```bash
php artisan serve
```

**Admin credentials**
- Email: `admin@example.com`
- Password: `12345678`

**If you want Employee user then register a user it will register as a employee.**

**If you want dummy data you can run below command**
```bash
php artisan db:seed --class=DatabaseSeeder
```

---

## Features

**User Registration and Authentication:**
- Implemented user registration and login functionality using Laravel’s built-in authentication ([Breeze](https://laravel.com/docs/11.x/starter-kits#laravel-breeze)).

**User Roles:**
- Uses Laravel’s gates to restrict access to resources and actions based on user roles.
- Implemented middleware to enforce role-based access.

**Task Managment**
- CRUD Operations for Tasks.
- Option for users to mark tasks as completed.
- List view of tasks with filters, in-progress list is shown default.
- Admins create and assign tasks to employees by default.
- Admins can grant specific permissions to employees to create or assign tasks.

**Permission Management**
- Interface for admins to grant or revoke task creation and assignment permissions for employees.

**User-Specific Tasks:**
- Depanding permission user can assign or create tasks.
- Ensure each user only sees tasks assigned and created by them.

---

## Design choices
- I chose to implement laravel component based design approach. clean separation & allow reusable. Also use [Bootstrap](https://getbootstrap.com/) for front-end design and responsiveness.

---

## Tech Stack

**Client:** HTML, CSS, Bootstrap, JavaScript, Jquery, Tippy.js

**Server:** PHP, Laravel

**Database:** MySQL
