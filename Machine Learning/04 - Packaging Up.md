
# Python

## Generators

Cuando iteras pero sin retornar la list entera

```python
def filter_data(data, condition):
    for x in data:
        if condition(x):
            yield x
```

```python
gen1 = (x**2 for x in range(10))
for i in gen1:
    print(i)
```

Estructuras a repasar

- **deque**
- **Counter**
- **OrderedDict**

# PySpark

El código se ha de escribir en **CamelCase**

Spark es principalmente programación tipo funcional, no orientada a objetos.

# Principios a seguir

## DRY

Don't repeat yourself

## Kiss

Keep it simple, stupid


# Building package

Para construir un package se utiliza la **setuptools** library


## Make files

Permite run, test and clean packages

## Poetry

Para gestionar dependencias y environments.



# Testing, loggin, securing and error handling

## Testing

**pytest**

## Security

Encontrar fallos de seguridad en el código

**Bandit package**

https://bandit.readthedocs.io/en/latest/

Para analizar dependencias para temas de seguridad

**safety** 

https://pypi.org/project/safety/


## Logging

**logging** library
