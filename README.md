## Version Control

- Create a **public GitHub repository**, for example: `dteam-django-practical-test`.
- Put the **text of this test (all instructions)** into your `README.md`.
- For each task, create a **separate branch**, e.g., `tasks/task-1`, `tasks/task-2`, etc.
- When finishing a task, **merge** that branch into `main`, but **do not delete** the task branch.

---

## Python Virtual Environment

- Use **pyenv** to manage the Python version.
  - Create a file named `.python-version` in the repo with the exact Python version.
- Use **Poetry** to manage dependencies.
  - This will create a `pyproject.toml` file.

Update your `README.md` with clear instructions on how to install and use **pyenv** and **Poetry** for this project.

---

## Tasks

### Task 1: Django Fundamentals

- Create a new Django project, e.g., `cvproject`.
- Use the Python version configured with `pyenv` and the latest stable Django.
- Use **SQLite** as the database (initially).
- Create a Django app, e.g., `main`.

#### Create a Model
Define a `CV` model with fields:
- `first_name`
- `last_name`
- `skills`
- `projects`
- `bio`
- `contacts`

Structure the data logically and efficiently.

#### Load Initial Data
- Create a **fixture** with at least one sample CV.
- Add instructions in `README.md` on how to load the fixture.

#### List Page View and Template
- Implement view `/` to show a list of CVs.
- Use any CSS library for styling.
- Ensure efficient database queries.

#### Detail Page View
- Implement view `/cv/<id>/` to show individual CV details.
- Apply proper styling and query optimization.

#### Tests
- Add basic tests for list and detail views.
- Document how to run tests in `README.md`.

---

### Task 2: PDF Generation

- Choose and install an **HTML-to-PDF** library.
- Add a **"Download PDF"** button on the CV detail page.

---

### Task 3: REST API

- Install **Django REST Framework (DRF)**.
- Create **CRUD endpoints** for the `CV` model.
- Add tests for each CRUD operation.

---

### Task 4: Middleware & Request Logging

#### Request Log Model
- Add to the existing app or create a new one (e.g., `audit`).
- Fields:
  - `timestamp`
  - `HTTP method`
  - `path`
  - *(optional)*: query string, remote IP, user

#### Logging Middleware
- Create middleware to log each request into the database.

#### Recent Requests Page
- View: `/logs/`  
- Show the **10 most recent requests**, sorted by timestamp (descending).
- Use a template to display: `timestamp`, `method`, `path`.

#### Tests
- Add tests to verify logging functionality.

---

### Task 5: Template Context Processors

- Create a **context processor** to inject `settings` into all templates.
- Create view `/settings/` to display values like `DEBUG`.

---

### Task 6: Docker Basics

- Use **Docker Compose** to containerize the project.
- Switch database from **SQLite → PostgreSQL**.
- Store environment variables in a `.env` file.

---

### Task 7: Celery Basics

- Install and configure **Celery**, using **Redis** or **RabbitMQ** as the broker.
- Add a **Celery worker** to `docker-compose`.

On the CV detail page:
- Add **email input**.
- Add **"Send PDF to Email"** button to trigger a Celery task that sends the CV PDF to the entered email.

---

### Task 8: OpenAI Basics

On the CV detail page:
- Add a **"Translate"** button and a **language selector**.

Support the following languages:
> Cornish, Manx, Breton, Inuktitut, Kalaallisut, Romani, Occitan, Ladino, Northern Sami, Upper Sorbian, Kashubian, Zazaki, Chuvash, Livonian, Tsakonian, Saramaccan, Bislama

Use the **OpenAI Translation API** or any other translation mechanism.

---

### Task 9: Deployment

- Deploy the project to **DigitalOcean** or another **VPS**.

---

## Final Notes

- Complete each task thoroughly.
- Follow the **branch & merge** structure for commits.
- Ensure your `README.md` includes:
  - Setup & installation
  - How to run the project
  - How to run tests
