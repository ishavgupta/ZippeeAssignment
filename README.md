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

# Step 4: Add apps to settings.py
# In taskmanager/settings.py:
INSTALLED_APPS = [
    ...
    'rest_framework',
    'rest_framework_simplejwt',
    'drf_yasg',
    'tasks',
]

# Configure REST Framework
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': (
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ),
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ],
}

# Step 5: Run initial migrations
python manage.py migrate
