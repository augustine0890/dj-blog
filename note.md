# Blog App Project with Django

## Blog App

**Static Files**
- Static files: CSS, JS, and images
- In a production-ready, static files would typically store on Content Delivery Network (CDN) for better performance.

## Accounts App
- Flow: `Sigup -> Login -> Homepage`

**Heroku Config**
- Update `Pipfile.lock`
`pipenv lock`
- New `Procfile`
`touch Procfile`
- Install `Gunicorn`
`pipenv install gunicorn==19.9.0`
- Update `settings.py`
