# Architecting systems

Siempre es importante tener un diseño en mente al construir software, especialmente en sistemas de aprendizaje automático (ML). Al igual que en la construcción de una casa, primero se debe entender y diseñar una solución que cumpla con los requisitos del cliente, iterando el plan con expertos antes de empezar.

Un buen diseño en software:

- Define los componentes necesarios.
- Explica cómo interactúan estos componentes.
- Muestra cómo se puede extender la solución en el futuro.
- Indica qué herramientas utilizar.
- Estipula el flujo de procesos y datos.

Sin un diseño adecuado, podríamos tener una base de código confusa, duplicar trabajo, seleccionar herramientas incompatibles y fallar en anticipar la infraestructura necesaria, lo que lleva a desorganización y retrasos. La arquitectura de software actúa como un plan claro y efectivo para guiar la construcción, asegurando que se resuelvan los problemas del usuario final. En el contexto de ML, esto es crucial para evitar estos problemas y construir soluciones efectivas.

# Building with principles

La arquitectura de software, al igual que cualquier disciplina madura, tiene principios consistentes que deben seguirse. Aquí se destacan algunos de estos principios y su aplicación en sistemas de aprendizaje automático (ML).

1. **Separación de Responsabilidades**: Asegura que los componentes de software no sean innecesariamente complejos y sean extensibles. En la práctica, se manifiesta en capas separadas dentro de las aplicaciones con responsabilidades distintas.
    
2. **Principio de la Menor Sorpresa**: Cualquier persona con conocimientos razonables en tu dominio no debería encontrar nada inusual en tu arquitectura. Esto facilita la comprensión y el uso eficiente de la arquitectura por parte de desarrolladores y científicos de datos.
    
3. **Principio del Menor Esfuerzo**: Los desarrolladores tenderán a seguir el camino de menor resistencia. Diseñar la arquitectura con cuidado asegura que sea fácil de mantener y extender a lo largo del tiempo.
    

### Principios de Diseño SOLID Adaptados a la Arquitectura

- **Responsabilidad Única**: Cada módulo debe tener una sola razón para cambiar, facilitando su mantenimiento.
- **Abierto/Cerrado**: Los componentes deben ser abiertos para extensión pero cerrados para modificación, permitiendo añadir nuevas funcionalidades sin reescribir el núcleo.
- **Sustitución de Liskov**: Los componentes intercambiables deben mantener el mismo comportamiento y contrato.
- **Segregación de Interfaces**: Minimizar los métodos de comunicación entre componentes, haciendo interfaces específicas para clientes.
- **Inversión de Dependencias**: Las comunicaciones entre módulos deben manejarse mediante abstracciones, no implementaciones concretas.

### Contextos Delimitados

Asegurar que los modelos de datos estén alineados con modelos conceptuales específicos y no sean un "libre para todos". En organizaciones grandes, cada unidad de negocio debe tener su propia base de datos y modelos, con contratos explícitos para unir información si es necesario.

Estos principios y prácticas ayudan a diseñar arquitecturas de ML que sean claras, mantenibles y escalables.

### Resumen: Explorando algunos patrones estándar de ML

#### Patrones Estándar en Arquitecturas de ML

En lugar de reinventar la rueda, debemos reutilizar y adaptar patrones bien conocidos para acelerar y robustecer nuestros proyectos de ML.

1. **Lagos de Datos**:
    
    - **Descripción**: Permiten almacenar cualquier tipo de datos a cualquier escala.
    - **Ventajas**: Flexibilidad para almacenar datos estructurados, semi-estructurados y no estructurados.
    - **Ejemplo**: AWS S3 es una solución que permite almacenar múltiples formatos de datos como fotos, archivos JSON y más.
    
1. **Microservicios**:
    
    - **Descripción**: Arquitectura donde los componentes funcionales están separados en servicios independientes.
    - **Ventajas**: Facilita el desarrollo, mantenimiento y despliegue independiente de servicios.
    - **Ejemplo**: En una aplicación web de compras, distintos microservicios pueden manejar recomendaciones de productos, previsiones de entregas, y promociones personalizadas.

1. **Diseños Basados en Eventos**:
    
    - **Descripción**: Las acciones individuales desencadenan otras acciones en el sistema, permitiendo un flujo de datos más dinámico.
    - **Tipos**:
        - **Pub/Sub**: Los datos de eventos se publican en un bus de mensajes para ser consumidos por otras aplicaciones (ej. Apache Kafka).
        - **Streaming de Eventos**: Procesa un flujo continuo de datos en tiempo real (ej. Apache Storm).
    - **Ventajas**: Permiten orquestación sofisticada y gestión dinámica de datos.

1. **Procesamiento por Lotes**:
    
    - **Descripción**: Procesamiento de datos en intervalos de tiempo regulares en lotes.
    - **Ventajas**: Planificación eficiente de recursos computacionales, manejo de grandes volúmenes de datos, optimización de criterios de procesamiento.
    - **Ejemplo**: Sistemas ETML (Extract, Transform, Machine Learning) que extraen, transforman y aplican algoritmos de ML a los datos.

### Conclusión

Estos patrones ayudan a construir soluciones de ML que son robustas, escalables y fáciles de mantener, aplicando principios probados y adaptándolos a las necesidades específicas de los proyectos de ML.

### Resumen: Contenerización

#### Contenerización de Aplicaciones

Para un ingeniero de ML, es crucial entender los requisitos ambientales del código y cómo diferentes entornos pueden afectar su ejecución. Esto es especialmente importante en Python, que necesita un intérprete y un entorno adecuado con las bibliotecas necesarias.

Una solución efectiva es la contenerización, que implica empaquetar una aplicación y sus dependencias en una unidad independiente que puede ejecutarse en cualquier plataforma. La tecnología de contenedores más popular es Docker, que es de código abierto y muy fácil de usar. Contenerizar aplicaciones ayuda a evitar problemas de compatibilidad y facilita el despliegue en distintos entornos.

**Alojando tu propio microservicio en AWS**

Una forma clásica de mostrar tus modelos de ML es a través de un servicio web ligero alojado en un servidor. Este puede ser un patrón de despliegue muy flexible.

Puedes ejecutar un servicio web en cualquier servidor con acceso a internet y, si está bien diseñado, a menudo es fácil agregar más funcionalidades a tu servicio web y exponerlas mediante nuevos endpoints.

En Python, los dos frameworks web más utilizados siempre han sido Django y Flask. En esta sección, nos centraremos en Flask, ya que es el más sencillo de los dos y ha sido ampliamente documentado para despliegues de ML en la web, por lo que podrás encontrar mucho material para complementar lo que aprendas aquí.

En AWS, una de las formas más simples de alojar tu solución web con Flask es como una aplicación en contenedores en una plataforma adecuada. Aquí repasaremos los aspectos básicos de cómo hacerlo, pero no dedicaremos tiempo a los aspectos detallados de mantener una buena seguridad web para tu servicio. Discutir esto completamente podría requerir un libro entero, y hay excelentes recursos más enfocados disponibles en otros lugares.

**Construcción de pipelines generales con Airflow**

En el Capítulo 4 discutimos los beneficios de escribir nuestro código de ML como pipelines, usando herramientas como sklearn y Spark ML. Estos pipelines simplificaban nuestro código, pero estaban limitados a un solo archivo Python y no permitían mucha flexibilidad ni sofisticación en los flujos de datos.

**Airflow**

Apache Airflow, desarrollado por Airbnb en la década de 2010 y de código abierto desde su inicio, es una herramienta de gestión de flujos de trabajo que permite a científicos e ingenieros de datos crear pipelines complejos programáticamente con scripts en Python. Airflow utiliza Gráficos Acíclicos Dirigidos (DAG) para definir y ejecutar tareas. Proporciona operadores predeterminados para definir DAGs que pueden usar múltiples componentes y también ofrece funcionalidad para programar tus pipelines. Por ejemplo, se puede construir un pipeline de Airflow que obtenga datos, realice ingeniería de características, entrene un modelo y lo persista.


## Construcción de pipelines avanzados de ML

Hemos discutido cómo SciKit-learn y Spark ML proporcionan mecanismos para crear pipelines de ML básicos. Ahora, existen herramientas avanzadas, tanto de código abierto como empresariales, que llevan este concepto al siguiente nivel.

**Proveedores de la nube:**

- **Amazon SageMaker:** Una solución completa de AWS para construir, monitorear y gestionar modelos de ML.
- **Google Vertex AI:** Herramienta de Google Cloud Platform para desarrollo y despliegue de ML, con mucha funcionalidad bajo una sola interfaz.
- **Azure ML:** La oferta de Microsoft para pipelines de ML.

Estas soluciones empresariales pueden ser probadas gratuitamente, pero pueden implicar costos cuando se escalan y pueden causar "vendor lock-in" debido a su integración con proveedores específicos.

**ZenML:**

ZenML es un framework completamente de código abierto que permite escribir pipelines de ML independientemente de la infraestructura subyacente. Permite que el entorno de desarrollo local y el de producción sean diferentes, y se pueden cambiar configuraciones sin alterar el núcleo de los pipelines.

**Conceptos clave de ZenML:**

- **Pipelines:** Definiciones de los pasos en el flujo de trabajo de ML.
- **Stacks:** Configuraciones del entorno y la infraestructura para ejecutar el pipeline.
- **Orchestrator:** Coordina los pasos del pipeline en la infraestructura. Puede ser el predeterminado o algo como Airflow o Kubeflow.
- **Artifact store:** Componente responsable del almacenamiento de datos y metadatos, compatible con AWS S3, Azure Blob Storage y Google Cloud Storage.

**Kubeflow**

Kubeflow es una solución de código abierto diseñada para proporcionar métodos portátiles para construir sistemas de ML de extremo a extremo. Este herramienta permite a los desarrolladores crear rápidamente pipelines para el procesamiento de datos, entrenamiento de modelos de ML, predicción y monitoreo, todo esto siendo independiente de la plataforma. Kubeflow utiliza Kubernetes, permitiendo desarrollar soluciones en diferentes entornos de los que se despliegan finalmente.

**Puntos clave de Kubeflow:**

- **Jupyter Notebook:** Aplicación web y controlador para análisis de datos exploratorios y modelado inicial.
- **Operadores de entrenamiento:** Incluyen PyTorch, TFJob y XGBoost para construir varios modelos.
- **Katib:** Capacidades para ajuste de hiperparámetros y búsqueda de arquitecturas de redes neuronales.
- **Operadores Spark:** Para la transformación de datos, incluyendo una opción para clústeres AWS EMR.
- **Dashboard:** Para interactuar con el clúster de Kubernetes y gestionar las cargas de trabajo de Kubeflow.
- **Kubeflow Pipelines:** Plataforma para construir, ejecutar y gestionar flujos de trabajo de ML de extremo a extremo, con un motor de orquestación y un SDK para trabajar con los pipelines.

Kubeflow ofrece una documentación detallada en [Kubeflow Documentation](https://www.kubeflow.org/docs/), ideal para profundizar en su arquitectura y principios de diseño.

## Seleccionando tu estrategia de despliegue

Hemos discutido detalles técnicos sobre cómo llevar soluciones de ML a producción, pero falta definir cómo manejar la infraestructura existente y cómo introducir la solución al tráfico real. Elegir una estrategia de despliegue adecuada es crucial para un ingeniero de ML.

**Estrategias de despliegue:**

- **Blue/green deployments:** La nueva versión del software se ejecuta junto a la existente hasta cumplir ciertos criterios, luego todo el tráfico se redirige al nuevo sistema. Esto es útil para recopilar datos de rendimiento antes del despliegue completo y permite retroceder si es necesario. Es ideal para trabajos por lotes, aunque puede ser costoso.
    
- **Canary deployments:** Similar al método blue/green, pero el tráfico se cambia gradualmente entre las dos soluciones. Inicialmente, el nuevo sistema recibe un pequeño porcentaje del tráfico, incrementando gradualmente. Es útil para microservicios de ML llamados en el backend de un sitio web, aunque puede no ser adecuado para grandes trabajos por lotes.
    

El Capítulo 8 mostrará cómo usar estas estrategias al construir un endpoint de ML personalizado usando Kubernetes.

**Resumen del capítulo:**

- Discutimos conceptos importantes para desplegar soluciones de ML, enfocándonos en arquitectura y herramientas para despliegue en la nube.
- Cubrimos patrones importantes en ingeniería de ML moderna y cómo implementarlos con contenedores y servicios de AWS.
- Exploramos herramientas avanzadas como Apache Airflow para orquestar pipelines y cómo integrarlas con GitHub Actions.
- Introdujimos ZenML y Kubeflow para desarrollar y desplegar pipelines de ML a gran escala.

El próximo capítulo abordará otras formas de escalar nuestras soluciones para manejar grandes volúmenes de datos y cálculos de alto rendimiento.