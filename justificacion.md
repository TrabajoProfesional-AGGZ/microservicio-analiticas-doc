---
layout: default
title: Justificación tecnológica
nav_order: 3
---

# 🛠️ Justificación tecnológica

En esta sección documentamos las decisiones técnicas tomadas para la construcción del microservicio de analíticas, asegurando que cada herramienta elegida aporte valor real al desarrollo y mantenimiento del producto.

## Lenguajes y frameworks

Para este microservicio, la selección de nuestra pila tecnológica se enfocó fuertemente en la capacidad de procesamiento de datos y la gestión de tareas en segundo plano:

* **Python:** Se eligió como lenguaje principal debido a su supremacía y vasto ecosistema en el área de análisis de datos y cálculo de métricas. Nos permite implementar lógicas complejas de fidelización y consolidación de forma limpia y mantenible.
* **FastAPI:** Seleccionado como framework web por su alto rendimiento y soporte asíncrono. Ideal para exponer los endpoints de consulta de métricas al dashboard web, garantizando respuestas rápidas mediante validación estricta (Pydantic) y autogenerando la documentación Swagger/OpenAPI.
* **Redis:** Fundamental en este microservicio. Se utiliza como *message broker* (agente de mensajes) para encolar y procesar eventos asíncronos (ej. `pagos_listener`). Esto desacopla la carga de procesamiento del flujo principal de la aplicación.
* **SQLAlchemy y Alembic:** Implementados para el modelado robusto de la base de datos relacional (donde persisten los KPIs consolidados) y el control seguro de versiones del esquema.
* **Pytest:** Adoptado para asegurar que los cálculos matemáticos de las métricas y la lógica de los *listeners* de eventos funcionen a la perfección, previniendo regresiones en la lógica de negocio.

## Integración y despliegue continuo (CI/CD)

La implementación de pipelines de CI/CD es fundamental en el microservicio para garantizar entregas ágiles y seguras. Nos permite automatizar la ejecución de pruebas y el despliegue a los distintos entornos, reduciendo el error humano y acelerando el *time-to-market*.

## Pruebas unitarias y Code Coverage

Para asegurar la robustez y estabilidad del código, mantenemos un estándar estricto de calidad:

* Se ha implementado una gran cantidad de pruebas unitarias cubriendo los casos de uso principales y casos borde.
* Mantenemos un **estricto nivel de Code Coverage** (cobertura de código) fijado en un mínimo del **90%**, el cual es validado automáticamente en cada Pull Request mediante nuestro pipeline.

## Documentación integral

Utilizamos **JustTheDocs** para mantener esta documentación viva, versionada junto con el código y fácilmente accesible para cualquier miembro del equipo. Esto centraliza el conocimiento y reduce los cuellos de botella en la comunicación.
