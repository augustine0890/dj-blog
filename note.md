# Blog App Project with Django

## Blog App

**Static Files**
- Static files: CSS, JS, and images
- In a production-ready, static files would typically store on Content Delivery Network (CDN) for better performance.

## Accounts App
- Flow: `Signup -> Login -> Homepage`

**Sign Up**
- Signup URL: `users/signup/`
- Login URL: `users/login/`
    - By default Django will look within a templates directory called `registration` for a file called `login.html` for a log in form.
    - [LoginView](https://docs.djangoproject.com/en/3.0/topics/auth/default/#django.contrib.auth.views.LoginView)

**Custom User Model**
-  The official documentation [example](https://docs.djangoproject.com/en/3.0/topics/auth/customizing/#a-full-example)
- Update `settings.py`
- Create a new `CustomUser` model

- Create new forms for `UserCreationForm` and `UserChangeForm`
`touch users/forms.py`

- Update `users/admin.py`
    - Delete `blog/migrations` and `db.sqlite3`
    - `python manage.py makemigrations users`
    - `python manage.py migrate`
    - `python manage.py createsuperuser` -> user/pw: `augustine/123`

Reference: [Custom User Model](https://learndjango.com/tutorials/django-custom-user-model)

**Heroku Config**
- Update `Pipfile.lock`
`pipenv lock`
- New `Procfile`
`touch Procfile`
- Install `Gunicorn`
`pipenv install gunicorn==19.9.0`
- Update `settings.py`
`ALLOWED_HOSTS = ['*']`

**Deployment**
- `heroku git:remote -a augustine-blog-dj`
- `git push heroku master`