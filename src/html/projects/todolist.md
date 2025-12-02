## Project Title & Badges 🚀

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A simple ToDo List application built with Laravel, designed to help users manage their tasks efficiently. 📝

<hr>

## Description 📝

The ToDo List application is a web-based tool designed to help users organize and manage their tasks effectively. Built using PHP and the Laravel framework, it provides essential features such as task creation, categorization, status tracking, and user authentication. The application uses a SQLite database for data storage and incorporates modern web development practices with Tailwind CSS for styling and Vite for asset bundling.

<hr>

## Table of Contents 🗂️

- [Project Title \& Badges 🚀](#project-title--badges-)
- [Description 📝](#description-)
- [Table of Contents 🗂️](#table-of-contents-️)
- [Features ✨](#features-)
- [Tech Stack 💻](#tech-stack-)
- [Installation 🛠️](#installation-️)
- [Usage 👨‍💻](#usage-)
- [How to Use 💡](#how-to-use-)
- [Project Structure 📂](#project-structure-)
- [Contributing 🤝](#contributing-)
- [Important Links 🔗](#important-links-)

<hr>

## Features ✨

- **User Authentication:** Secure registration and login functionality. 🔐
- **Task Management:** Create, edit, and delete tasks. ✅
- **Categorization:** Organize tasks into predefined categories (cat1, cat2, cat3). 🗂️
- **Status Tracking:** Monitor task progress with status options (To Do, In Progress, Done). 📊
- **Filtering and Searching:** Filter tasks by category and status, and search by title. 🔍
- **Email Notifications**: Sends email when task is created. 📧

<hr>

## Tech Stack 💻

- **Backend:** PHP 8.2, Laravel 12
- **Frontend:** JavaScript, Bootstrap, Tailwind CSS, Next.js
- **Database:** SQLite
- **Build Tools:** Vite

<hr>

## Installation 🛠️

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/phobo22/todolist.git
    cd todolist
    ```
2.  **Install PHP dependencies:**
    ```bash
    composer install
    ```
3.  **Copy the environment file:**
    ```bash
    cp .env.example .env
    ```
4.  **Generate application key:**
    ```bash
    php artisan key:generate
    ```
5.  **Set up the database:**
    ```bash
    php artisan migrate
    ```
6.  **Install JavaScript dependencies:**
    ```bash
    npm install
    ```
7.  **Build assets:**
    ```bash
    npm run build
    ```

<hr>

## Usage 👨‍💻

1.  **Run the development server:**
    ```bash
    php artisan serve
    ```
2.  **Access the application** in your browser at `http://localhost:8000`.
3.  **Register or login** to manage your tasks.
4.  **Use the navigation** to add, view, and manage your tasks.

<hr>

## How to Use 💡

1.  **Register/Login:**
    - Navigate to the `/register` or `/login` routes.
    - Use the forms to create a new account or log in with existing credentials.

    ```php
    Route::get('/register', 'register')
        ->middleware('guest')
        ->name('register.page');
    ```

2.  **Task Management:**
    - **Add Task:** Click on "Add Task" in the navigation bar to create a new task.

    ```php
    Route::get('/tasks/create', 'create')
        ->middleware('auth')
        ->name('tasks.create');
    ```

    - **View Tasks:** Click on "Your Task" to see a list of tasks. Here, you can:
        - Filter tasks by category and status.
        - Search tasks by title.
        - Update or delete tasks if you have the required permissions.

    ```php
    Route::get('/tasks', 'index')
        ->middleware('auth')
        ->name('tasks.index');
    ```

    - **Update Task:** Click the “Update” button on a task to edit its details.

    ```php
    Route::put('/tasks/{task}', 'update')
        ->middleware('auth')
        ->can('edit', 'task')
        ->name('tasks.update');
    ```

    - **Delete Task:** Click the “Delete” button to remove a task.

    ```php
    Route::delete('/tasks/{task}', 'destroy')
        ->middleware('auth')
        ->can('edit', 'task')
        ->name('tasks.destroy');
    ```
<hr>

## Project Structure 📂

```
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   ├── Jobs/
│   ├── Mail/
│   ├── Models/
│   ├── Providers/
├── bootstrap/
├── config/
├── database/
│   ├── factories/
│   ├── migrations/
│   ├── seeders/
├── public/
├── resources/
│   ├── css/
│   ├── js/
│   ├── views/
│   │   ├── auth/
│   │   ├── components/
│   │   ├── home/
│   │   ├── layouts/
│   │   ├── mail/
│   │   ├── task/
├── routes/
├── storage/
├── tests/
├── .env.example
├── package.json
├── vite.config.js
├── composer.json
├── composer.lock
```
<hr>

## Contributing 🤝

Contributions are welcome! Please follow these steps:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Commit your changes with descriptive messages.
4.  Push your branch to your forked repository.
5.  Create a pull request to the main repository.

<hr>

## Important Links 🔗

- Repository: [https://github.com/phobo22/todolist](https://github.com/phobo22/todolist)
