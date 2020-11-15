# Django Test

The original tutorial is forked from https://yeasy.gitbook.io/docker_practice/compose/django .

However, there are several bugs in the mentioned tutorial. 



First, when you add  `postgres` in `docker-compose.yml`, you must claim several Environment Variables under the `environment`, including: `POSTGRES_USER`, `POSTGRES_DB`, `POSTGRES_OASS`

```JSON
db:
	image: postgres
	environment:
	  POSTGRES_USER: postgres
      POSTGRES_DB: postgres
      POSTGRES_PASSWORD: postgres
    ports:
      - "5432:5432"
```

In `settings.py`

```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': 'postgres',
        'USER': 'postgres',
        'HOST': 'db',
        'PASSWORD': 'postgres',
        'PORT': 5432,
    }
}
```

