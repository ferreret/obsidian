Permite guardar contraseñas y/o api keys para que no sean expuestas.
Esta información queda separada del código.

No utilizar environment variables.

**Secrets Manager**

Se guardan por proyecto proyectos, no son globales como los environment variables

Hay que tener en cuenta la jerarquía de donde se pueden pillar las configuraciones.
Mirar PDF para ver el orden, si existe en dos o más sitio la misma clase, se sobreescribe con la última.

**Inicializar User Secrets**

Hay que ejecutarlo desde la carpeta del proyecto donde hay el archivo \*.csproj

```bash
dotnet user-secrets init
```

**Crear una clave nueva**

En el siguiente ejemplo damos valor a Password

```bash
dotnet user-secrets set "Password" "usususus"
```

**Añadir un package al proyecto**

```zsh
dotnet add package Microsoft.Extensions.Hosting
```


### NOTA

En el ejemplo de la aplicación de consola, hay que tener en cuenta que cuando se añaden los tipos de configuración, el último que se añada es el que prevalece si la clave está tanto en el json como en los user secrets.