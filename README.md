# Zeotap
Assignment Submission
Here's a sample **README.md** that combines both the **Rule Engine System with AST** and the **Weather Monitoring System** into a single GitHub repository. You can customize this further based on specific details of your implementation.

---

# Rule Engine System with AST & Weather Monitoring System

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Rule Engine System with AST](#rule-engine-system-with-ast)
  - [How it Works](#how-it-works)
  - [Endpoints](#endpoints)
  - [Getting Started](#getting-started)
- [Weather Monitoring System](#weather-monitoring-system)
  - [How it Works](#how-it-works-1)
  - [Endpoints](#endpoints-1)
  - [Getting Started](#getting-started-1)
- [Running the Project](#running-the-project)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This repository contains two primary applications:
1. **Rule Engine System with AST (Abstract Syntax Tree):** A 3-tier application that allows users to define, combine, and evaluate complex business rules using an Abstract Syntax Tree (AST) to make decisions based on dynamic conditions.
2. **Weather Monitoring System:** A system that monitors weather data and provides updates for specific locations, using external APIs for real-time weather data.

Both systems are implemented with separate functionalities but can be integrated together into a larger service-oriented architecture.

---

## Features

### Rule Engine System with AST
- Create complex business rules dynamically.
- Store and retrieve rules for evaluation using an AST.
- Combine multiple rules for efficient evaluations.
- Evaluate conditions based on provided user data.

### Weather Monitoring System
- Fetch current weather data using APIs.
- Monitor temperature, humidity, and other weather conditions.
- Save and retrieve weather reports for specific locations.

---

## Tech Stack

- **Backend Framework:** Flask (Python)
- **Database:** SQLite (can be replaced with other databases)
- **APIs:** OpenWeather API for real-time weather data
- **Testing:** Pytest for unit tests
- **Other:** UUID for unique rule identification, JSON for data interchange

---

## Rule Engine System with AST

### How it Works

The Rule Engine allows users to define and evaluate business rules based on input data. These rules are stored in-memory and structured as ASTs for efficient evaluation. Rules can be combined to create complex logical operations.

Example rule:
```python
rule1 = "(age > 30 AND department = 'Sales') OR (salary > 50000)"
```

### Endpoints

1. **Create a Rule**
   - **Endpoint:** `/create_rule`
   - **Method:** `POST`
   - **Request Body:**
     ```json
     {
       "rule": "(age > 30 AND department = 'Sales') OR (salary > 50000)"
     }
     ```
   - **Response:**
     ```json
     {
       "ast_id": "unique-ast-id"
     }
     ```

2. **Evaluate a Rule**
   - **Endpoint:** `/evaluate`
   - **Method:** `POST`
   - **Request Body:**
     ```json
     {
       "ast_id": "unique-ast-id",
       "data": {
         "age": 35,
         "department": "Sales",
         "salary": 60000
       }
     }
     ```
   - **Response:**
     ```json
     {
       "result": true
     }
     ```

### Getting Started

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/repository-name.git
   cd repository-name
   ```

2. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Flask Application**
   ```bash
   flask run
   ```

---

## Weather Monitoring System

### How it Works

This system fetches real-time weather data using an external weather API (like OpenWeather) and allows users to query weather conditions for specific cities or locations.

### Endpoints

1. **Get Weather by City**
   - **Endpoint:** `/weather/<city_name>`
   - **Method:** `GET`
   - **Response:**
     ```json
     {
       "city": "New York",
       "temperature": 25,
       "humidity": 60,
       "condition": "Cloudy"
     }
     ```

### Getting Started

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/repository-name.git
   cd repository-name
   ```

2. **Set up API keys**
   - Sign up for the OpenWeather API and get your API key.
   - Add the API key to the environment variables or configuration file.

3. **Run the Flask Application**
   ```bash
   flask run
   ```

---

## Running the Project

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/repository-name.git
   cd repository-name
   ```

2. **Set up a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the application:**
   ```bash
   flask run
   ```

5. **Access the APIs:**
   - Rule Engine: `http://localhost:5000/create_rule`
   - Weather Monitoring: `http://localhost:5000/weather/<city_name>`

---

## Testing

This project uses `pytest` for unit testing. 

1. **Run Tests**
   ```bash
   pytest
   ```

2. **Test Cases**
   - **Rule Engine:** Test rule creation, combination, and evaluation logic.
   - **Weather Monitoring:** Test weather data fetching and validation.

---

## Contributing

Contributions are welcome! Please follow these steps to contribute:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m 'Add feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a pull request.

---
