# DTI412 Lab 02 — Course Portal

A Django course portal exercise featuring a course overview, course details, and a student inquiry form. Course information is currently stored in the app's in-memory sample data.

## Features

- Home page with a featured course and course count
- Course listing and individual course detail pages
- Inquiry form with basic required-field and email checks
- Django admin route

Inquiry submissions are validated and shown on the page; this lab does not save them to a database. Course records are sample data defined in `catalog/views.py`.

## Built with

- Python
- Django 5.2
- SQLite (Django's default local database)

## Project layout

```text
.
├── catalog/          # Course pages, inquiry form, and templates
├── courseportal/     # Django project settings and URL configuration
├── manage.py
└── README.md
```

## Run locally

Python 3.10 or newer is recommended.

1. Clone the repository and enter its folder:

   ```bash
   git clone https://github.com/chitkokolwin/dti412-lab02.git
   cd dti412-lab02
   ```

2. Create and activate a virtual environment:

   **Windows PowerShell**
   ```powershell
   py -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```

   **macOS / Linux**
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. Install Django:

   ```bash
   python -m pip install "Django==5.2.19"
   ```

4. Set a fresh development secret key for this shell session:

   **Windows PowerShell**
   ```powershell
   $env:DJANGO_SECRET_KEY = (py -c "from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())")
   ```

   **macOS / Linux**
   ```bash
   export DJANGO_SECRET_KEY="$(python -c 'from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())')"
   ```

   The secret key must stay private. The key previously committed in this repository should be considered exposed; use a newly generated key and never commit it.

5. Apply database migrations and start the development server:

   ```bash
   python manage.py migrate
   python manage.py runserver
   ```

6. Open http://127.0.0.1:8000/ in your browser.

For local development, `DEBUG` defaults to `False` and allowed hosts default to `localhost,127.0.0.1`. Set `DJANGO_DEBUG=True` only in a local development shell. For deployment, configure `DJANGO_ALLOWED_HOSTS` with the exact host names and follow Django's deployment checklist.

## License

See [LICENSE](LICENSE).
