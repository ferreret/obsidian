- Sirve para encapsular el acceso a la BBDD.
- Es más fácil mantener el código
## Referencias a añadir

**EntityFramework**

```bash
dotnet add package Microsoft.EntityFrameworkCore
```

```bash
dotnet add package Microsoft.EntityFrameworkCore.Design
```

```bash
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
```


Comprobamos que **docker** está funcionando:

```bash
docker ps
```

Para un SQL Server, el archivo **docker-compose.yaml** tiene la siguiente estructura:

```yaml
version: '3.8'
	services:
		sqlserver:
			image: "mcr.microsoft.com/mssql/server:2019-latest"
			environment:
				ACCEPT_EULA: "Y"
				SA_PASSWORD: "pa55w0rd!"
				MSSQL_PID: "Express"
			ports:
				- "1433:1433"
```

Para poner en marcha el docker

```bash
docker compose up -d
```

**NOTA** Solo me funciona si no lo ejecuto desde una unidad montada.

## Migrations

Iniciar la migración, crea la BBDD según modelos y AppDbContext

``` bash
dotnet ef migrations add InitialMigration
```

Después de iniciar la migración, hay que actualizar la base de datos

```bash
dotnet ef database update
```

### Redis

``` bash
dotnet add package Microsoft.Extensions.Caching.StackExchangeRedis
```
