# 📦 Project Setup

---

# 🧩 1. Install Homebrew (Mac Only)

> Skip this step if you're on Windows.

Homebrew is a package manager for macOS.  
You’ll use it to easily install Git, Python, Docker, etc.

**Install Homebrew:**

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**Verify Homebrew:**

```bash
brew --version
```

If you see a version number, you're good to go.

---

# 🧩 2. Install and Configure Git

## Install Git

- **MacOS (using Homebrew)**

```bash
brew install git
```

- **Windows**

Download and install [Git for Windows](https://git-scm.com/download/win).  
Accept the default options during installation.

**Verify Git:**

```bash
git --version
```

---

## Configure Git Globals

Set your name and email so Git tracks your commits properly:

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

Confirm the settings:

```bash
git config --list
```

---

# 🧩 3. Clone the Repository

Now you can safely clone the course project:

```bash
git clone <repository-url>
cd <repository-directory>
```

---

# 🛠️ 4. Install Python 3.10+

## Install Python

- **MacOS (Homebrew)**

```bash
brew install python
```

- **Windows**

Download and install [Python for Windows](https://www.python.org/downloads/).  
✅ Make sure you **check the box** `Add Python to PATH` during setup.

**Verify Python:**

```bash
python3 --version
```
or
```bash
python --version
```

---

## Create and Activate a Virtual Environment

(Optional but recommended)

```bash
python3 -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate.bat  # Windows
```

### Install Required Packages

```bash
pip install -r requirements.txt
```

---

# 🐳 5. (Optional) Docker Setup

> Skip if Docker isn't used in this module.

## Install Docker

- [Install Docker Desktop for Mac](https://www.docker.com/products/docker-desktop/)
- [Install Docker Desktop for Windows](https://www.docker.com/products/docker-desktop/)

## Build Docker Image

```bash
docker build -t <image-name> .
```

## Run Docker Container

```bash
docker run -it --rm <image-name>
```

---

# 🚀 6. Running the Project

- **Without Docker**:

```bash
python main.py
```

(or update this if the main script is different.)

- **With Docker**:

```bash
docker run -it --rm <image-name>
```

---

# 7. Running Tests Locally

To run the test suite locally, follow these steps.

## Clone the repository

```bash
git clone <your-github-repository-url>
cd assignment11
```

## Create and activate a virtual environment
```bash
python -m venv venv
source venv/bin/activate
```

## Install dependencies
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

## Configure the database

Make sure PostgreSQL is installed and running. Configure the DATABASE_URL environment variable to point to your PostgreSQL database.

For example:
```bash
export DATABASE_URL="postgresql://user:password@localhost:5432/mytestdb"
```
On Windows PowerShell:
```bash
$env:DATABASE_URL="postgresql://user:password@localhost:5432/mytestdb"
```
Use your own PostgreSQL credentials and database name.

## Run the tests

Run the complete test suite:
```bash
pytest
```
To run individual test categories:
```bash
pytest tests/unit/
pytest tests/integration/
pytest tests/e2e/
```
To generate a test coverage report:
```bash
pytest --cov=app --cov-report=term-missing
```
The test suite includes unit tests, integration tests, and end-to-end tests for the calculator application, user functionality, calculation models, and Pydantic schema validation.

Note: Integration tests require a properly configured PostgreSQL database. End-to-end tests also require the application server and Playwright browser dependencies to be available.

---

# 8. Docker Hub Repository

The Docker image is available on Docker Hub:

https://hub.docker.com/r/ps223/assignment11

Pull the image:

```bash
docker pull ps223/assignment11
```

---