
Vamos a ver como solucionar los problemas en cuatro pasos

1. Descubrir
2. Jugar
3. Desarrollar
4. Desplegar

Vamos a utilizar **Jira** para administrar las tareas y **AWS** para aprovisionar la infraestructura e implementar la solución.

| **Descubrir** | Claridad en la cuestión empresarial.<br><br>Argumentos claros a favor del ML frente a otro enfoque.<br><br>Definición de los KPIs y métricas que se quieren optimizar.<br><br>Un esbozo de la ruta hacia el valor. |
| ---- | ---- |
| **Jugar** | Comprensión detallada de los datos.<br><br>Prueba de concepto funcional.<br><br>Acuerdo sobre el modelo/algoritmo/lógica que resolverá el problema.<br><br>Evidencia de que una solución es factible dentro de escenarios de recursos realistas.<br><br>Evidencia de que se puede lograr un buen retorno de la inversión. |
| **Desarrollar** | Una solución funcional que se puede alojar en una infraestructura adecuada y disponible.<br><br>Resultados de pruebas exhaustivos y métricas de rendimiento (para algoritmos y software).<br><br>Una estrategia acordada de reentrenamiento y despliegue de modelos.<br><br>Pruebas unitarias, pruebas de integración y pruebas de regresión.<br><br>Envasado de soluciones y ductos. |
| **Desplegar** | Un proceso de implementación funcional y probado.<br><br>Infraestructura provista con características apropiadas de seguridad y desempeño.<br><br>Modo de reciclaje y procesos de gestión.<br><br>¡Una solución de trabajo de principio a fin! |

#### CRISP-DM

Es otra metodología con diferentes pasos

## Poetry

```bash
pip install poetry
```

Crear nuevo proyecto
```bash 
poetry new project-name
```

Archivo pyproject.toml

```toml
[tool.poetry.dependencies]
scikit-learn="*"
```

Instalar dependencias
```bash
poetry install
```

## Control de versiones

![[Pasted image 20240229164929.png]]

## MLFlow 

Registra expermientos y metricas de rendimiento de los modelos

## CD/CI

![[Pasted image 20240229170049.png]]

https://mlflow.org/#core-concepts

