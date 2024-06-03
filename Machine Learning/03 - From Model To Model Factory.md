

Cuando se entrena un modelo, se ha de tener en cuenta que no siempre va a funcionar, este concepto se llama **drift**

![[Pasted image 20240315141701.png]]

Si se detecta cambios en el rendimiento del modelo, ha de provocar un reentrenamiento del sistema.

### Train-Run

El entrenamiento y la predicción se realizan en el mismo momento.
El entrenamiento puede ser por batch o incremental.

No es recomendable por defecto.

![[Pasted image 20240522102452.png]]

### Train-persist

![[Pasted image 20240522125630.png]]


## Retraining required

A lo largo del tiempo los modelos se degradan por desviación en los datos.


## Detection data drift

```python
pip install alibi
pip install alibi-detect
```

Podemos calcular deriva en los datos, tanto en las features, como en notebook de ejemplo, como en los labels, si es un problema de clasificación.

Tambien hay el **concept drift** que plantea la deriva cuando cambian las relaciones entre las variables del modelo.


### Feature importance

Puede depender del modelo o no, mirar ejemplo código libro.

## Como solucionar la deriva

- **Borrar features y reentrenar**
- **Reentrenar con más datos** También podemos entrenar solo con la ventana de datos que nos interese.
- **Reemplazar el modelo**
- **Reescribir o debugar la solución**
- **Fix el origen de datos**

## Evidently AI

Librería opensource para ver derivas, que ofrece gráficos interactivos.


## Optimización en la búsqueda de hiperparámetros

### Hyperopt

Librería opensource

https://github.com/Hyperopt/Hyperopt


### Optuna

También es una librería opensource para búsqueda de hiperparámetros

## AutoML

### auto-sklearn

### AutoKeras

https://autokeras.com/

Funciona para redes neuronales.


## Persisting models

### MLFlow
https://mlflow.org/docs/latest/introduction/index.html


## Pipelines

### Scikit-learn pipelines

Mirar FunctionTransformer para el caso de transformaciónes complicadas

### Spark ML pipelines
