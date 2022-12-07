
### Crear proyecto Django

```sh
django-admin startproject mysite
```

### Migración de base de datos

```sh
python manage.py migrate
```


### Crear una aplicación

```sh
python3 manage.py startapp blog
```

### Mostrar shell

Sirve para interactuar con los modelos

```sh
python3 manage.py shell
```

### Initial migration for app

```sh
python manage.py makemigrations blog
```

### Inspect migration
```sh
python manage.py sqlmigrate blog 0001
```

### Apply migration
```sh
python manage.py migrate
```

### Creating superuser

```sh
python manage.py createsuperuser
```
