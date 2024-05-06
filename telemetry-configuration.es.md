---
description: "Mejora tu configuración de LearnPack con telemetría para desbloquear insights clave y optimizar la gestión de tus cursos."
---

# Mejora tu experiencia en LearnPack con la configuración de telemetría

Descubre el poder de LearnPack y lleva la gestión de tus cursos al siguiente nivel configurando la telemetría. Esta característica no se trata solo de recopilar datos; se trata de desbloquear percepciones que pueden revolucionar el viaje de aprendizaje. Pero, ¿cómo configuras la ruta para telemetry.json o transmites eventos a medida que ocurren?

### Simplifica con learn.json

Cada curso de LearnPack viene con un archivo `learn.json`, tu centro de mando para la prueba de ejercicios, selección de compiladores y más. La clave "telemetry" es la última innovación aquí, diseñada para agilizar tu seguimiento de datos.

Echa un vistazo a este ejemplo de configuración de la clave de telemetría:
![Ejemplo de Clave de Telemetría](https://github.com/breatheco-de/content/assets/107764250/70caf7ad-89df-4ead-9404-d7778cd6dd15)

Para los usuarios registrados, LearnPack siempre está al tanto, transmitiendo eventos para interacciones clave:
- Al presionar el botón "siguiente" (evento: open_step)
- Ejecutar código con el botón "ejecutar" (evento: compile)
- Lanzar pruebas con el botón "ejecutar pruebas" (evento: test)
- Consultar al tutor de IA (evento: ai_interaction)

Asegúrate de que tus URLs de transmisión y lote estén configuradas para recibir solicitudes POST. Está en tus manos idear la lógica que destilará los datos esenciales de estas interacciones.

¡Adéntrate en el mundo de la configuración de telemetría y eleva la experiencia educativa con LearnPack!
