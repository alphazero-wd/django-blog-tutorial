### How to run this app on your local machine

#### Prerequisites

1. Packages

   You need to have all of these following packages installed:

- [Python 3.7 or above](https://python.org)
- [Docker Desktop](https://www.docker.com/products/docker-desktop/)

2. Libraries

- `django-environ`: adding environment variables to a Django project in order to hide secret, sensitive data
- `Pillow`: working with file uploads
- `crispy_forms` and `crispy_bootstrap5`: formatting/styling Django forms

```
pip install django-environ Pillow crispy_forms crispy_bootstrap5
```

3. Setting up the project

   1. At the top level of the project, create a `docker.env` file and add all of the following variables:

   ```bash
   export POSTGRES_USER="user"
   export POSTGRES_PASSWORD="password"
   export POSTGRES_DB="django_blog"
   export PGADMIN_DEFAULT_EMAIL="user@email.com"
   export PGADMIN_DEFAULT_PASSWORD="password"
   ```

   2. Create a `.env` file in the `django_blog` folder and add all of the following variables:

   ```bash
   export DATABASE_NAME="django_blog"
   export DATABASE_USER="user"
   export DATABASE_PASSWORD="password"
   export DATABASE_HOST="localhost"
   export DATABASE_PORT=5432
   export SECRET_KEY="secret-key"
   ```

   3. Once Docker Desktop is installed, in the root project folder, run the following command

   ```
   docker-compose up
   ```

   4. Run the following command to apply migrations to the database

   ```
   python manage.py migrate
   ```

   5. Start the server at `localhost:8000`

   ```
   python manage.py runserver
   ```
