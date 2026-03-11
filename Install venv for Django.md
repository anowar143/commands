# 🔹 Tutorial: Setting up venv for Django / DRF on Windows 11

This guide will help you set up a **Python virtual environment (venv)** and install **Django + Django REST Framework** on **Windows 11**.

---

## 1️⃣ Install Python (if not already installed)

Download the latest **Python 3.x** from:

👉 https://www.python.org/downloads/

During installation, make sure you check:

```
✅ Add Python to PATH
```

### Verify Installation

Open **Command Prompt** or **PowerShell** and run:

```bash
python --version
```

or

```bash
py --version
```

---

## 2️⃣ Open Command Prompt / PowerShell

Press:

```
Win + R → type cmd → Enter
```

Or search for **PowerShell** in the Start menu.

---

## 3️⃣ Navigate to Your Project Folder

Example:

```bash
cd C:\Users\YourName\Projects\my_django_project
```

---

## 4️⃣ Create a Virtual Environment

Run the following command:

```bash
python -m venv env
```

`env` is the virtual environment folder name (you can also name it `venv`).

This creates a **separate Python environment** just for your Django / DRF project.

### Folder Structure Example

```
my_django_project/
│
├── env/
```

---

## 5️⃣ Activate the Virtual Environment

Run:

```bash
env\Scripts\activate
or
.\env\Scripts\activate
```

After activation, you’ll see `(env)` before your command prompt:

```
(env) C:\Users\YourName\Projects\my_django_project>
```

### Deactivate Later

```bash
deactivate
```

---

## 6️⃣ Upgrade pip

While inside the virtual environment:

```bash
pip install --upgrade pip
```

---

## 7️⃣ Install Django & Django REST Framework

```bash
pip install django djangorestframework
```

### Check Installed Versions

```bash
django-admin --version
```

```bash
pip show djangorestframework
```

---

## 8️⃣ Freeze Requirements (Recommended)

Create a `requirements.txt` file:

```bash
pip freeze > requirements.txt
```

This allows you to reinstall dependencies later using:

```bash
pip install -r requirements.txt
```

---

## 9️⃣ Start a Django Project (Test)

Create a Django project:

```bash
django-admin startproject myproject .
```

Run the development server:

```bash
python manage.py runserver
```

Open in your browser:

```
http://127.0.0.1:8000/
```

---

# ✅ Success!

You now have a **working Django + Django REST Framework setup** inside a **virtual environment on Windows 11**.

---

## 📌 Quick Command Summary

```bash
python -m venv env
.\env\Scripts\activate
pip install --upgrade pip
pip install django djangorestframework
django-admin startproject myproject .
python manage.py runserver
```
