# Local development

Use Python 3.10 or later. From the repository root:

```sh
cd honeybot-project
python -m venv .venv
. .venv/bin/activate
python -m pip install -r requirements.txt
export DJANGO_SECRET_KEY="$(python -c 'import secrets; print(secrets.token_urlsafe(50))')"
export DJANGO_DEBUG=true
python manage.py migrate
python manage.py runserver 127.0.0.1:8000
```

Commands above use a POSIX shell. In PowerShell, activate with `.venv\Scripts\Activate.ps1` and set variables using `$env:DJANGO_SECRET_KEY` and `$env:DJANGO_DEBUG`.

Mail is printed to the development console by default. To enable SMTP deliberately, set `DJANGO_EMAIL_BACKEND=django.core.mail.backends.smtp.EmailBackend`, `EMAIL_HOST_USER`, and `EMAIL_HOST_PASSWORD`. Never commit their values. This configuration reads the process environment; it does not automatically load a .env file.

## Credential incident

An SMTP credential was previously committed. Revoke that app password at the email provider; replacing this file does not remove it from Git history. Existing tracked databases, archives, and caches remain tracked despite .gitignore and need a separate data review.

## Deployment

Debug mode defaults to false and a secret key is required. Configure `DJANGO_ALLOWED_HOSTS` explicitly, use HTTPS and a production application server, and run `python manage.py check --deploy` before deployment. These changes are not a complete security audit.
