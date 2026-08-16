---
layout: default
title: Inicio
nav_order: 1
description: "Documentacion del microservicio de analíticas de SocioUnido"
---

# Microservicio de analíticas

Microservicio encargado de la consolidación de KPIs, procesamiento de eventos y métricas de fidelización de "SocioUnido".

## Utilidad y funcionalidad

El microservicio de analíticas está diseñado para manejar las siguientes responsabilidades clave:

* **Consolidación de métricas y KPIs:** Actúa como el motor principal para calcular y almacenar indicadores clave de rendimiento (ej. morosidad, ingresos, retención de socios), procesando datos provenientes de otros módulos del sistema.
* **Procesamiento de eventos asíncronos:** Escucha y procesa eventos críticos del negocio (como la confirmación de pagos o altas de socios) mediante colas de mensajes, asegurando que las métricas se actualicen en tiempo real sin bloquear la experiencia del usuario.
* **Motor de fidelización:** Administra las reglas de negocio relacionadas con el comportamiento del socio, calculando *scores* y métricas de lealtad para potenciar la retención.

## ¿Qué vas a encontrar en esta página?

A continuación, se detalla toda la información técnica, arquitectónica y organizativa sobre esta implementación en particular:

* 🔌 **[Endpoints](endpoints.html):** Documentación estática y detallada de la API, ideal para consultar integraciones.
* 🛠️ **[Justificación tecnológica](justificacion.html):** El porqué de los lenguajes y frameworks elegidos, nuestro pipeline de CI/CD, la estrategia de testing y métricas de Code Coverage definidas.
* 🏗️ **[Arquitectura y diagramas](diagramas.html):** Representación visual de la arquitectura del microservicio utilizando el modelo C4.
* 📊 **[Métricas de la implementación](metricas.html):** Estadísticas del desarrollo, cantidad de commits, Pull Requests y distribución del trabajo en el equipo.
