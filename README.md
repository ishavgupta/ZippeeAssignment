# Project Setup Instructions


# Step 1: Create and activate a virtual environment

python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Step 2: Install required packages

pip install django djangorestframework djangorestframework-simplejwt drf-yasg

# Step 3: Create project and app

django-admin startproject taskmanager
cd taskmanager
python manage.py startapp tasks

# Step 4: Run initial migrations
python manage.py makemigrations
python manage.py migrate


# Step 5: Runserver

python manage.py runserver
