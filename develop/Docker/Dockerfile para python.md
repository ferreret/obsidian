### Dockerfile

```sh
FROM python:3.8
WORKDIR /app
COPY requirements.txt requirements.txt
RUN pip install --no-cache-ddir --upgrade -r /app/requirements
COPY . /app
CMD bash -c "while true; do sleep 1; done"
```


### docker-compose.yml

```yaml
services: 
	app-csv:
		build:
			context: .
			dockerfile: Dockerfile
	volumes:
		- .:/app		
```

### Construir el contenedor

```sh
docker-compose build
```

### Levantamos contenedor

```sh
docker-compose up -d
```

### Ejecutar bash en el contenedor

```sh
docker-compose exec app-csv bash
```