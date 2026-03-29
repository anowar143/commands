# 🚀 Django + PostgreSQL Project Setup Guide (Windows 11)

A complete guide to setting up your Django project with PostgreSQL on a fresh Windows 11 machine.

---

## 📋 Table of Contents

- [Prerequisites](#prerequisites)
- [Step 1 — Fix PowerShell Execution Policy](#step-1--fix-powershell-execution-policy)
- [Step 2 — Install Python](#step-2--install-python)
- [Step 3 — Install PostgreSQL](#step-3--install-postgresql)
- [Step 4 — Clone or Locate the Project](#step-4--clone-or-locate-the-project)
- [Step 5 — Create & Activate Virtual Environment](#step-5--create--activate-virtual-environment)
- [Step 6 — Install Dependencies](#step-6--install-dependencies)
- [Step 7 — Configure Environment Variables](#step-7--configure-environment-variables)
- [Step 8 — Setup the Database](#step-8--setup-the-database)
- [Step 9 — Run the Project](#step-9--run-the-project)
- [Troubleshooting](#troubleshooting)

---

## Prerequisites

Make sure you have the following before starting:

| Tool | Recommended Version | Download |
|------|-------------------|---------|
| Python | 3.10+ | [python.org](https://www.python.org/downloads/) |
| PostgreSQL | 15+ | [postgresql.org](https://www.postgresql.org/download/windows/) |
| Git | Latest | [git-scm.com](https://git-scm.com/download/win) |
| pip | Comes with Python | — |

---

## Step 1 — Fix PowerShell Execution Policy

> ⚠️ **Fresh Windows 11 machines block script execution by default.** This prevents the virtual environment from activating.

Open **PowerShell** and run:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

**What this does:**
- `RemoteSigned` — allows locally created scripts to run freely; downloaded scripts must be signed
- `Scope CurrentUser` — applies only to your account, keeping the system secure

Verify the change:

```powershell
Get-ExecutionPolicy -Scope CurrentUser
# Expected output: RemoteSigned
```

---

## Step 2 — Install Python

1. Download Python from [python.org](https://www.python.org/downloads/)
2. During installation, **check** ✅ `Add Python to PATH`
3. Verify the installation:

```powershell
python --version
# Expected: Python 3.x.x

pip --version
# Expected: pip xx.x.x
```

> 💡 If `python` is not recognized, restart PowerShell or your PC after installation.

---

## Step 3 — Install PostgreSQL

1. Download PostgreSQL from [postgresql.org](https://www.postgresql.org/download/windows/)
2. Run the installer and note your:
   - **Port** (default: `5432`)
   - **Superuser password** (you set this during install)
3. After install, open **pgAdmin** or **psql** and create a database for your project:

```sql
CREATE DATABASE ontheviz_db;
CREATE USER ontheviz_user WITH PASSWORD 'yourpassword';
GRANT ALL PRIVILEGES ON DATABASE ontheviz_db TO ontheviz_user;
```

> 💡 You can also use **pgAdmin** (GUI) if you prefer not to use the command line.

---

## Step 4 — Clone or Locate the Project

**If the project is already on your local disk (e.g. `E:\Projects\ontheviz`):**

```powershell
cd E:\Projects\ontheviz
```

**If you need to clone from GitHub:**

```powershell
git clone https://github.com/your-username/ontheviz.git
cd ontheviz
```

---

## Step 5 — Create & Activate Virtual Environment

> 🗑️ **Delete any old `env` folder** from your previous machine — it contains paths and binaries tied to the old system.

```powershell
# Remove old env (if exists)
Remove-Item -Recurse -Force env

# Create a fresh virtual environment
python -m venv env

# Activate it
env\Scripts\activate
```

You should now see `(env)` at the start of your terminal prompt:

```
(env) PS E:\Projects\ontheviz>
```

---

## Step 6 — Install Dependencies

With the virtual environment active, install all required packages:

```powershell
pip install -r requirements.txt
```

> 💡 If `psycopg2` fails to install (PostgreSQL adapter), try:
> ```powershell
> pip install psycopg2-binary
> ```

Verify installed packages:

```powershell
pip list
```

---

## Step 7 — Configure Environment Variables

Create a `.env` file in the root of your project:

```powershell
# Create the file
New-Item -Name ".env" -ItemType File
```

Open `.env` and add your configuration:

```env
# Django
SECRET_KEY=your-secret-key-here
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1

# PostgreSQL Database
DB_NAME=ontheviz_db
DB_USER=ontheviz_user
DB_PASSWORD=yourpassword
DB_HOST=localhost
DB_PORT=5432
```

Make sure your `settings.py` reads from this file. If you're using `python-decouple` or `django-environ`, it should look like:

```python
# settings.py (example using python-decouple)
from decouple import config

SECRET_KEY = config('SECRET_KEY')
DEBUG = config('DEBUG', default=False, cast=bool)

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': config('DB_NAME'),
        'USER': config('DB_USER'),
        'PASSWORD': config('DB_PASSWORD'),
        'HOST': config('DB_HOST', default='localhost'),
        'PORT': config('DB_PORT', default='5432'),
    }
}
```

> 🔒 Make sure `.env` is listed in your `.gitignore` so secrets are never committed.

---

## Step 8 — Setup the Database

Run Django migrations to create the database tables:

```powershell
# Apply migrations
python manage.py migrate

# (Optional) Create a superuser for Django Admin
python manage.py createsuperuser
```

---

## Step 9 — Run the Project

```powershell
python manage.py runserver
```

Open your browser and visit:

```
http://127.0.0.1:8000/
```

Django Admin panel:

```
http://127.0.0.1:8000/admin/
```

---

## Troubleshooting

### ❌ `env\Scripts\activate` — scripts disabled

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

---

### ❌ `python` or `pip` not recognized

- Reinstall Python and check ✅ **"Add Python to PATH"** during setup
- Or manually add `C:\Users\<YourUser>\AppData\Local\Programs\Python\Python3x\` to your system PATH

---

### ❌ `psycopg2` installation fails

```powershell
pip install psycopg2-binary
```

---

### ❌ `django.db.utils.OperationalError` — can't connect to database

- Make sure PostgreSQL service is running:
  ```powershell
  Get-Service -Name postgresql*
  ```
- Double-check `.env` credentials match what you set during PostgreSQL installation

---

### ❌ `ModuleNotFoundError` after activating env

Your env may be outdated. Recreate it:

```powershell
Remove-Item -Recurse -Force env
python -m venv env
env\Scripts\activate
pip install -r requirements.txt
```

---

## 📁 Project Structure (Reference)

```
ontheviz/
├── env/                  # Virtual environment (DO NOT commit)
├── ontheviz/             # Django project settings
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── apps/                 # Your Django apps
├── requirements.txt      # Python dependencies
├── .env                  # Environment variables (DO NOT commit)
├── .gitignore
└── manage.py
```

---

## 📝 Recommended `.gitignore` Entries

```gitignore
# Virtual environment
env/
venv/
.venv/

# Environment variables
.env

# Python cache
__pycache__/
*.pyc
*.pyo

# Django
*.log
db.sqlite3

# VS Code
.vscode/
```

---

> Made with ❤️ for the **ontheviz** project. Happy coding! 🎉
