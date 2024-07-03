# Django Weather App.

<div align="center">
  <img src="weather_project/images/django logo.png" alt="Descripción de la Imagen">
</div>

<div align="center">
  <video width="600" controls>
    <source src="https://www.youtube.com/watch?v=HF-DfZvor-8" type="video/mp4">
    Your browser does not support the video tag.
  </video>
</div>

## Índice.
1. [Descripción del Proyecto](#descripción-del-proyecto)
2. [Tecnologías y Librerías Utilizadas](#tecnologías-y-librerías-utilizadas)
3. [Rendimiento](#rendimiento)
4. [Mejoras Futuras](#mejoras-futuras)
5. [Api´s a conectar](#apis-a-conectar)
6. [Proceso ETL](#proceso-etl)
7. [Arquitectura Model-View-Template](#arquitectura-model-view-template)
8. [Conclusión](#conclusión)

### 1. Descripción del Proyecto.
Esta aplicación en Django proporciona información del clima en tiempo real para diferentes ciudades utilizando una API externa. Es un proyecto de conexión de APIs, diseñado para ser escalable a distintas industrias y mejorar el flujo de información, procesamiento, ahorro de tiempo y costos, y obtención de datos en tiempo real.

### 2. Tecnologías y Librerías Utilizadas.
| Tecnología/Librería | Tipo | Función |
|---------------------|------|---------|
| Django              | Framework | Framework principal del proyecto |
| requests            | Librería | Realiza solicitudes HTTP a la API de OpenWeatherMap |
| Python              | Lenguaje | Lenguaje de programación utilizado para el desarrollo del proyecto |
| Html/CSS              | Lenguaje | Tecnologías para la creación de las vistas. |

### 3.Rendimiento.
El rendimiento del script es eficiente, capaz de procesar y mostrar datos en tiempo real. Las solicitudes a la API son rápidas, y el procesamiento de datos es manejado eficientemente por el servidor Django en un sistema Windows 11 Pro.

### 4.Mejoras Futuras.
El proyecto puede escalarse e integrarse con diversas tecnologías y servicios, como:

#### Servicios para Industrias Específicas:
 - Agricultura: Proveer datos climáticos para planificación de cultivos y gestión de recursos.
 - Transporte y Logística: Información en tiempo real para optimización de rutas y planificación de entregas.
 - Turismo: Ofrecer a los turistas información climática precisa y recomendaciones.

#### Análisis de Datos y Ciencia de Datos:
 - Análisis Predictivo: Usar datos históricos para predecir tendencias y patrones climáticos.
 - Visualización de Datos: Crear dashboards interactivos con herramientas como Tableau o Power BI.
 - Minería de Datos: Extraer información valiosa de grandes conjuntos de datos climáticos.

#### Inteligencia Artificial y Productividad:
 - Automatización de Tareas: Usar IA para automatizar procesos repetitivos relacionados con el clima.
 - Asistentes Virtuales: Implementar chatbots para responder preguntas sobre el clima en tiempo real.

#### Integraciones con Plataformas:
 - Google Cloud APIs: Para procesamiento y análisis de datos a gran escala.
 - AWS: Para almacenamiento y servicios de computación.
 - Kubernetes: Para gestión de contenedores y escalabilidad.
 - BigQuery y Dataflow: Para análisis y procesamiento de grandes volúmenes de datos.

#### Automatización y Escalabilidad:
 - CI/CD Pipelines: Para despliegue y mantenimiento continuo.
 - Machine Learning: Para predicciones climáticas basadas en datos históricos y en tiempo real.

#### Facturación y Servicios Financieros:
 - Integración de Facturación: Automatizar la facturación para servicios climáticos personalizados.
 - Servicios Financieros: Ofrecer asesoramiento basado en datos climáticos para seguros y financiamiento agrícola.

#### Conexiones a Bases de Datos:
 - Bases de Datos SQL/NoSQL: Integración con bases de datos como PostgreSQL, MongoDB para almacenamiento de datos climáticos históricos.
 - Data Warehousing: Implementación de almacenes de datos para análisis avanzado.

#### Observabilidad y Controles:
 - Monitoreo en Tiempo Real: Implementar soluciones de monitoreo para la infraestructura del proyecto.
 - Alertas y Notificaciones: Configurar alertas para cambios climáticos críticos.

### 5. Api´s a conectar.

| API    | Descripción | Funciones |
|------------|-------------|-------------|
| **Analytics Hub API** | Analytics Hub proporciona una manera fácil de publicar, descubrir y suscribirse para compartir conjuntos de datos de BigQuery entre usuarios de su organización u otras organizaciones. Una vez que crea un intercambio, puede invitar a otros a publicar o suscribirse a datos en el intercambio. | Compartir y gestionar conjuntos de datos de BigQuery |
| **NetApp Cloud Volumes Service** | NetApp Cloud Volumes Service para Google Cloud es un servicio de almacenamiento de archivos totalmente gestionado en la nube con capacidades avanzadas de gestión de datos que ofrecen el rendimiento, la disponibilidad y la seguridad necesarios para ejecutar cargas de trabajo empresariales. Comience una prueba: reduzca los costos de infraestructura hasta en un 70%. Comience hoy con una prueba gratuita de NetApp Cloud Volumes Service. Cloud Volumes Service viene con nuestro servicio de incorporación complementario que ayudará a afinar la configuración de su entorno y garantizar la mejor experiencia posible. | Almacenamiento y gestión de datos en la nube |
| **Cloud Natural Language API** | Proporciona tecnologías de comprensión del lenguaje natural, como análisis de sentimientos, reconocimiento de entidades, análisis de sentimientos de entidades y otras anotaciones de texto, a los desarrolladores. | Análisis de texto, comprensión del lenguaje natural |
| **Document AI Warehouse** | Document AI Warehouse es una plataforma de gestión de documentos de extremo a extremo impulsada por IA que le permite almacenar, buscar y gestionar sus documentos en GCP. La misión de Google es organizar la información del mundo y hacerla universalmente accesible y útil. A través de productos y plataformas como Search, Maps, Gmail, Android, Google Play, Chrome y YouTube, Google desempeña un papel significativo en la vida diaria de miles de millones de personas. | Gestión y búsqueda de documentos mediante IA |
| **AI Platform Training & Prediction API** | Una API para habilitar la creación y el uso de modelos de aprendizaje automático. Proporciona herramientas específicas de MLOps para que los científicos de datos y los ingenieros de AA automaticen, estandaricen y administren proyectos de AA. Más de 130 modelos y herramientas de IA generativa. | Creación y gestión de modelos de aprendizaje automático |
| **Gmail** | Con la API de Gmail, puede ver y gestionar datos del buzón de Gmail como hilos, mensajes y etiquetas. | Gestión y análisis de correos electrónicos |

### 6. Proceso ETL.

Este proyecto puede entenderse como un proceso ETL:

| Proceso    | Descripción | Código |
|------------|-------------|--------|
| **Extracción** | Obtención de datos de la API de OpenWeatherMap. | `requests.get(current_weather_url.format(city, api_key)).json()` en `weather_app/views.py` |
| **Transformación** | Procesamiento y transformación de datos JSON en un formato adecuado para la presentación. | `fetch_weather` en `weather_app/views.py` |
| **Carga** | Presentación de los datos transformados en la interfaz web. | `render(request, 'weather_app/index.html', context)` en `weather_app/views.py` |


### 7. Arquitectura Model-View-Template.

El proyecto sigue la arquitectura MVT (Model-View-Template) de Django:

| Componente | Descripción | Código |
|------------|-------------|--------|
| **View**   | Controla la lógica y maneja las solicitudes del usuario. | `weather_app/views.py` |
| **Template** | Define la estructura y el diseño de la interfaz de usuario. | `templates/weather_app/index.html`, `templates/weather_app/city_weather.html` |
| **Model**  | No se utiliza directamente en este proyecto, ya que no hay almacenamiento en base de datos. | N/A |

### 8. Conclusión
Este proyecto demuestra cómo una aplicación Django puede ser utilizada para proporcionar información en tiempo real mediante la integración con APIs externas. La escalabilidad y las posibles mejoras futuras hacen de este proyecto una base sólida para desarrollar soluciones más complejas y útiles en diversas industrias.
