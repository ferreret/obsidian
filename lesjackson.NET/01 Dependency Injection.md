
Es una solución para evitar multiples dependencias encadenadas de diferentes partes de la arquitectura a la misma clase, por ejemplo, un DBRepository.
Es para mantener mejor el código en arquitecturas complejas.

- Permite intercambiar implementaciones facilmente.
- Es más fácil hacer unit testing


**Comprobar versión dotnet**

```bash
dotnet --version
```

**Crear minimal API**

```bash
dotnet new webapi -minimal -n DiApi
```

**Ejecutar con hotreload**

```bash
dotnet watch
```

**Ejecutar normal**

```bash
dotnet run
```

*Nota, si hay errores al ejecutar, comprobar si se ha de instalar lo siguiente*

```bash
dotnet dev-certs https --trust
```


## IServiceProvider

Es un contenedor de servicios, que provee instancias del servicio a utilizar.
No siempre hace falta pero es recomendable crear un contenedor.

![[Screenshot_20240514_135338.png]]

## Service lifetimes

- **Transient**
	- Se crea cada vez que se necesita
	- Mejor para servicios ligeros
	- Mejor opción por defecto
	- Multi-threading & memory leaks no requieren una gran consideración

- **Scoped**
	- Se crea por "scope"
	- Se crean por cada request
	- Utilizar cuando se necesita datos a persistir en todo un request

- **Singleton**
	- Solo se crea una vez
	- Existe por todo el tiempo de vida de la aplicación
	- Hay que tener en cuenta las consideración el multi-threading


## IScopedFactory

Ver video al respecto, es el penúltimo.
Es una interface por defecto que ya se inyecta para utilizarla.
