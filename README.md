# Gaming Blog

This a backend API for a gaming blog to post video game reviews and get comments from readers. It's developed with Python/Django, Docker and Postgres.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine.

### Prerequisites

- You need to have Docker installed on your machine.


### Install, build and run the application

Clone the repo:

```
git clone https://github.com/tunjayjafarli/gamingblog.git
```

Build and run the application with docker-compose:

```
cd gamingblog
docker-compose up --build
```

Now apply the migrations:
```
docker exec -it gamingblog_web_1 python manage.py migrate
```

The app should be up and running now. Browse to: `localhost:8000/api/` to view the API endpoints.

### API 

Posts API: `localhost:8000/api/posts/` - create, update, retrieve, and delete posts

Comments API: `localhost:8000/api/comments/` - create, update, retrieve, and delete comments

Users API: `localhost:8000/api/users/` - create, update, retrieve, and delete users

### Django admin

Django admin is also available at `localhost:8000/admin/` but you will need a staff account (i.e. superuser) to view it.
To create a superuser:
```
docker exec -it gamingblog_web_1 python manage.py createsuperuser
```
and follow the prompts to enter an email and password.


## Running the tests

There aren't any tests currently since it was out of the scope for this assignment; however, automated Django test suites can be run inside the web container with:
```
docker exec -it web python manage.py test
```

## Deployment

```
docker-compose up
```
or
```
docker-compose restart web
```

## Built With

* [Django](https://docs.djangoproject.com/en/2.1/) - The web framework used
* [Django REST framework](https://www.django-rest-framework.org/) - REST framework used
* [Docker](https://docs.docker.com/) - Container management

