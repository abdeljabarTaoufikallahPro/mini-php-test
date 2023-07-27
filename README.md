# Mini PHP Test

Write a REST API in php:

Your task is to provide the client with management app for their own Robot Factory. Employees, robots, robot models, and components.

NB: Authentication is optional

Language required: PHP

Framework: you could use any framework of your choice: preferably [symfony](https://symfony.com/) or [laravel](https://laravel.com/).

Recommended: [API Platform](https://api-platform.com/)

## The main entities:

### Employee
| Name       | Type     |
|------------|----------|
| id         | integer  |
| name       | varchar  |
| email      | varchar  |
| position   | varchar  |
| hire_date  | date     |
| created_at | datetime |
| updated_at | datetime |

### Model

| Name         | Type                            |
|--------------|---------------------------------|
| id           | integer                         |
| name         | varchar                         |
| manufacturer | varchar                         |
| description  | text                            |
| cost         | numeric                         |
| created_at   | datetime                        |
| updated_at   | datetime                        |
| components   | array of Component [ManyToMany] |

### Robot

| Name            | Type                                    |
|-----------------|-----------------------------------------|
| id              | integer                                 |
| serial_number   | varchar                                 |
| model_id        | integer - foreign key to Model table    |
| employee_id     | integer - foreign key to Employee table |
| production_date | date                                    |
| status          | varchar                                 |
| created_at      | datetime                                |
| updated_at      | datetime                                |
| components      | array of Component [ManyToMany]         |

### Component

| Name        | Type       |
|-------------|------------|
| id          | (integer)  |
| name        | (varchar)  |
| description | (text)     |
| cost        | (numeric)  |
| created_at  | (datetime) |
| updated_at  | (datetime) |

## Description of the API

### Employees:

- `GET /employees` Get all employees
- `POST /employees` Create a new employee
- `GET /employees/{id}` Get employee details
- `PUT /employees/{id}` Update employee details
- `DELETE /employees/{id}` Delete an employee

### Robot Models:

- `GET /models` Get all robot models
- `POST /models` Create a new robot model
- `GET /models/{id}` Get a robot model
- `PUT /models/{id}` Update a robot model
- `DELETE /models/{id}` Delete a robot model

### Robots:

- `GET /robots` Get all robots
- `POST /robots` Create a new robot
- `GET /robots/{id}` Get a robot 
- `PUT /robots/{id}` Update a robot
- `DELETE /robots/{id}` Delete a robot

### Components:

- `GET /components` Get all components
- `POST /components` Create a new component
- `GET /components/{id}` Get a component
- `PUT /components/{id}` Update a component
- `DELETE /components/{id}` Delete a component
