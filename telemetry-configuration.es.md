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


### ¿Cada cuánto se envía la telemetría?
La telemetría va acumulando eventos para enviarlos en situaciones clave:
#### Batch
- Luego de ejecutar `learnpack start`: Al iniciar el ejercicio de LearnPack, si la telemetría está configurada, se enviará por primera vez la misma.
- Al abrir un nuevo paso: Luego de que se va de un paso al siguiente, se marca ese siguiente paso como iniciado y se envía la copia actual de la telemetría al **batch** url configurado.

#### Stream
- Para cada nuevo evento, si el url para stream está configurado, LearnPack enviará información del mismo a través de un webhook al endpoint especificado.

> Recuerda: Para que la telemetr funcione y se envíe correctamente, deberás configurar ambos urls como se especifica anteriormente.

## ¿Cuál es la estructura de la telemetría?
En la telemetría se guarda información sobre cada ejercicio que se abre y cuándo lo hizo, los resultados para cada compilación o testeo, cada sesión de trabajo, cuando se inició por primera vez el tutorial y dónde se está trabajando e identificadores para la telemetría y el estudiante en caso de que sea un estudiante de 4Geeks.

Este es un ejemplo de cómo luce la telemetría:
```json
{
    "telemetry_id": "atlbmot8wvalltng",
    "slug": "prompt-engineering-for-beginners",
    "agent": "vscode",
    "tutorial_started_at": 1718211567826,
    "steps": [
        {
            "slug": "00-welcome",
            "position": 0,
            "files": [
                {
                    "path": "exercises\\00-welcome/README.es.md",
                    "name": "README.es.md",
                    "hidden": true
                },
                {
                    "path": "exercises\\00-welcome/README.md",
                    "name": "README.md",
                    "hidden": true
                },
                {
                    "path": "exercises\\00-welcome/__pycache__",
                    "name": "__pycache__",
                    "hidden": true
                }
            ],
            "ai_interactions": [],
            "compilations": [],
            "tests": [],
            "is_testeable": false
        },
        {
            "slug": "01.1-obtain-api-key",
            "position": 3,
            "files": [
                {
                    "path": "exercises\\01.1-obtain-api-key/app.py",
                    "name": "app.py",
                    "hidden": false
                },
                {
                    "path": "exercises\\01.1-obtain-api-key/README.es.md",
                    "name": "README.es.md",
                    "hidden": true
                },
                {
                    "path": "exercises\\01.1-obtain-api-key/README.md",
                    "name": "README.md",
                    "hidden": true
                },
                {
                    "path": "exercises\\01.1-obtain-api-key/test.py",
                    "name": "test.py",
                    "hidden": true
                },
                {
                    "path": "exercises\\01.1-obtain-api-key/__pycache__",
                    "name": "__pycache__",
                    "hidden": true
                }
            ],
            "ai_interactions": [],
            "compilations": [
                {
                    "stderr": "DQpbbm90aWNlXSBBIG5ldyByZWxlYXNlIG9mIHBpcCBhdmFpbGFibGU6IDIyLjMuMSAtPiAyNC4wDQpbbm90aWNlXSBUbyB1cGRhdGUsIHJ1bjogcHl0aG9uLmV4ZSAtbSBwaXAgaW5zdGFsbCAtLXVwZ3JhZGUgcGlwDQo=",
                    "stdout": "RW50ZXIgeW91ciBBUEkga2V5OiBSZXF1aXJlbWVudCBhbHJlYWR5IHNhdGlzZmllZDogcHl0aG9uLWRvdGVudiBpbiBjOlx1c2Vyc1xsZWdpb25cYXBwZGF0YVxsb2NhbFxwcm9ncmFtc1xweXRob25ccHl0aG9uMzExXGxpYlxzaXRlLXBhY2thZ2VzIChmcm9tIC1yIHJlcXVpcmVtZW50cy50eHQgKGxpbmUgMSkpICgxLjAuMSkNClJlcXVpcmVtZW50IGFscmVhZHkgc2F0aXNmaWVkOiBncm9xIGluIGM6XHVzZXJzXGxlZ2lvblxhcHBkYXRhXGxvY2FsXHByb2dyYW1zXHB5dGhvblxweXRob24zMTFcbGliXHNpdGUtcGFja2FnZXMgKGZyb20gLXIgcmVxdWlyZW1lbnRzLnR4dCAobGluZSAyKSkgKDAuOC4wKQ0KUmVxdWlyZW1lbnQgYWxyZWFkeSBzYXRpc2ZpZWQ6IGFueWlvPDUsPj0zLjUuMCBpbiBjOlx1c2Vyc1xsZWdpb25cYXBwZGF0YVxsb2NhbFxwcm9ncmFtc1xweXRob25ccHl0aG9uMzExXGxpYlxzaXRlLXBhY2thZ2VzIChmcm9tIGdyb3EtPi1yIHJlcXVpcmVtZW50cy50eHQgKGxpbmUgMikpICg0LjQuMCkNClJlcXVpcmVtZW50IGFscmVhZHkgc2F0aXNmaWVkOiBkaXN0cm88Miw+PTEuNy4wIGluIGM6XHVzZXJzXGxlZ2lvblxhcHBkYXRhXGxvY2FsXHByb2dyYW1zXHB5dGhvblxweXRob24zMTFcbGliXHNpdGUtcGFja2FnZXMgKGZyb20gZ3JvcS0+LXIgcmVxdWlyZW1lbnRzLnR4dCAobGluZSAyKSkgKDEuOS4wKQ0KUmVxdWlyZW1lbnQgYWxyZWFkeSBzYXRpc2ZpZWQ6IGh0dHB4PDEsPj0wLjIzLjAgaW4gYzpcdXNlcnNcbGVnaW9uXGFwcGRhdGFcbG9jYWxccHJvZ3JhbXNccHl0aG9uXHB5dGhvbjMxMVxsaWJcc2l0ZS1wYWNrYWdlcyAoZnJvbSBncm9xLT4tciByZXF1aXJlbWVudHMudHh0IChsaW5lIDIpKSAoMC4yNy4wKQ0KUmVxdWlyZW1lbnQgYWxyZWFkeSBzYXRpc2ZpZWQ6IHB5ZGFudGljPDMsPj0xLjkuMCBpbiBjOlx1c2Vyc1xsZWdpb25cYXBwZGF0YVxsb2NhbFxwcm9ncmFtc1xweXRob25ccHl0aG9uMzExXGxpYlxzaXRlLXBhY2thZ2VzIA==",
                    "signal": "SIGTERM",
                    "memoryUsage": 532480,
                    "cpuUsage": 0,
                    "errorType": "run-time",
                    "starting_at": 1718211884140,
                    "source_code": "aW1wb3J0IG9zDQojIERPIE5PVCBDSEFOR0UgVEhJUyBDT0RFDQoNCg0KQVBJX0tFWSA9IGlucHV0KCJFbnRlciB5b3VyIEFQSSBrZXk6ICIpDQoNCiMgU2F2ZSB0aGUgQVBJX0tFWSBpbiB0aGUgZG90ZW52IGZpbGUNCndpdGggb3BlbigiLmVudiIsICJ3IikgYXMgZjoNCiAgICBmLndyaXRlKGYiR1JPUV9BUElfS0VZPXtBUElfS0VZfVxuIikNCg0KIyBFeHBvcnQgdGhlIEFQSV9LRVkgYXMgYW4gZW52aXJvbm1lbnQgdmFyaWFibGUNCm9zLmVudmlyb25bIkdST1FfQVBJX0tFWSJdID0gQVBJX0tFWQ0KDQojIEluc3RhbGwgdGhlIGRlcGVuZGVuY2llcyBpbiB0aGUgcmVxdWlyZW1lbnRzLnR4dCBmaWxlDQpwcmludCgiSW5zdGFsbGluZyBkZXBlbmRlbmNpZXMuLi4iKQ0Kb3Muc3lzdGVtKCJwaXAgaW5zdGFsbCAtciByZXF1aXJlbWVudHMudHh0IikNCg==",
                    "ended_at": 1718211886645,
                    "exit_code": null
                }
            ],
            "tests": [
                {
                    "starting_at": 1718211893013,
                    "source_code": "aW1wb3J0IG9zDQojIERPIE5PVCBDSEFOR0UgVEhJUyBDT0RFDQoNCg0KQVBJX0tFWSA9IGlucHV0KCJFbnRlciB5b3VyIEFQSSBrZXk6ICIpDQoNCiMgU2F2ZSB0aGUgQVBJX0tFWSBpbiB0aGUgZG90ZW52IGZpbGUNCndpdGggb3BlbigiLmVudiIsICJ3IikgYXMgZjoNCiAgICBmLndyaXRlKGYiR1JPUV9BUElfS0VZPXtBUElfS0VZfVxuIikNCg0KIyBFeHBvcnQgdGhlIEFQSV9LRVkgYXMgYW4gZW52aXJvbm1lbnQgdmFyaWFibGUNCm9zLmVudmlyb25bIkdST1FfQVBJX0tFWSJdID0gQVBJX0tFWQ0KDQojIEluc3RhbGwgdGhlIGRlcGVuZGVuY2llcyBpbiB0aGUgcmVxdWlyZW1lbnRzLnR4dCBmaWxlDQpwcmludCgiSW5zdGFsbGluZyBkZXBlbmRlbmNpZXMuLi4iKQ0Kb3Muc3lzdGVtKCJwaXAgaW5zdGFsbCAtciByZXF1aXJlbWVudHMudHh0IikNCg==",
                    "ended_at": 1718211893606,
                    "stdout": "G1sxbT09PT09PT09PT09PT09PT09PT09PT09PT09PT09IHRlc3Qgc2Vzc2lvbiBzdGFydHMgPT09PT09PT09PT09PT09PT09PT09PT09PT09PT0bWzBtDQpwbGF0Zm9ybSB3aW4zMiAtLSBQeXRob24gMy4xMS4zLCBweXRlc3QtOC4yLjIsIHBsdWdneS0xLjUuMA0Kcm9vdGRpcjogQzpcVXNlcnNcTEVHSU9OXFByb2plY3RzXGpvYnNcNGdlZWtzXHR1dG9yaWFsc1xwcm9tcHQtZW5nDQpwbHVnaW5zOiBhbnlpby00LjQuMCwgdGVzdGRveC0zLjEuMA0KY29sbGVjdGVkIDEgaXRlbQ0KDQpleGVyY2lzZXNcMDEuMS1vYnRhaW4tYXBpLWtleVx0ZXN0LnB5IBtbMzJtLhtbMG0bWzMybSAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICBbMTAwJV0bWzBtDQoNChtbMzJtPT09PT09PT09PT09PT09PT09PT09PT09PT09PT09IBtbMzJtG1sxbTEgcGFzc2VkG1swbRtbMzJtIGluIDAuMDNzG1swbRtbMzJtID09PT09PT09PT09PT09PT09PT09PT09PT09PT09PRtbMG0NCg==",
                    "stderr": "",
                    "exit_code": 0
                }
            ],
            "is_testeable": true,
            "opened_at": 1718211866688,
            "completed_at": 1718211893606
        },
        {
            "slug": "02-write-your-first-prompt-",
            "position": 4,
            "files": [
                {
                    "path": "exercises\\02-write-your-first-prompt-/prompt.txt",
                    "name": "prompt.txt",
                    "hidden": false
                },
                {
                    "path": "exercises\\02-write-your-first-prompt-/README.es.md",
                    "name": "README.es.md",
                    "hidden": true
                },
                {
                    "path": "exercises\\02-write-your-first-prompt-/README.md",
                    "name": "README.md",
                    "hidden": true
                },
                {
                    "path": "exercises\\02-write-your-first-prompt-/test.py",
                    "name": "test.py",
                    "hidden": true
                },
                {
                    "path": "exercises\\02-write-your-first-prompt-/__pycache__",
                    "name": "__pycache__",
                    "hidden": true
                }
            ],
            "ai_interactions": [],
            "compilations": [],
            "tests": [
                {
                    "starting_at": 1718211911284,
                    "ended_at": 1718211913734,
                    "stdout": "G1sxbT09PT09PT09PT09PT09PT09PT09PT09PT09PT09IHRlc3Qgc2Vzc2lvbiBzdGFydHMgPT09PT09PT09PT09PT09PT09PT09PT09PT09PT0bWzBtDQpwbGF0Zm9ybSB3aW4zMiAtLSBQeXRob24gMy4xMS4zLCBweXRlc3QtOC4yLjIsIHBsdWdneS0xLjUuMA0Kcm9vdGRpcjogQzpcVXNlcnNcTEVHSU9OXFByb2plY3RzXGpvYnNcNGdlZWtzXHR1dG9yaWFsc1xwcm9tcHQtZW5nDQpwbHVnaW5zOiBhbnlpby00LjQuMCwgdGVzdGRveC0zLjEuMA0KY29sbGVjdGVkIDMgaXRlbXMNCg0KZXhlcmNpc2VzXDAyLXdyaXRlLXlvdXItZmlyc3QtcHJvbXB0LVx0ZXN0LnB5IBtbMzJtLhtbMG0bWzMybS4bWzBtG1szMW1GG1swbRtbMzFtICAgICAgICAgICAgICAgICAgICAgICAgWzEwMCVdG1swbQ0KDQo9PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09IEZBSUxVUkVTID09PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09DQobWzMxbRtbMW1fX19fX19fX19fX19fX19fX19fX19fX19fX19fX19fX18gdGVzdF9wcm9tcHQgX19fX19fX19fX19fX19fX19fX19fX19fX19fX19fX19fG1swbQ0KDQogICAgQHB5dGVzdC5tYXJrLml0KCJUaGUgcHJvbXB0IE1VU1QgaW5jbHVkZSBpbmZvcm1hdGlvbiBhYm91dCB0aGUgY2hhcmFjdGVycywgdGhlIHNjZW5lLCBhbmQgYXQgbGVhc3Qgb25lIG1vcmUgZWxlbWVudC4iKQ0KICAgIGRlZiB0ZXN0X3Byb21wdCgpOg0KICAgICAgICBQUk9NUFQgPSBvcGVuKHBhdGgsICJyIikucmVhZCgpDQogICAgICAgIHJlc3VsdCA9IGNyZWF0ZV9wcm9tcHQoVEVTVEVSX1BST01QVCwgUFJPTVBUKQ0KICAgIA0KICAgICAgICBpZiAiQkFEX1BST01QVCIgaW4gcmVzdWx0Og0KICAgICAgICAgICAgc2F2ZV9yZXBvcnQocmVzdWx0KQ0KICAgICAgICBlbHNlOg0KICAgICAgICAgICAgZGVsZXRlX3JlcG9ydCgpDQogICAgDQo+ICAgICAgIGFzc2VydCAiR09PRF9QUk9NUFQiIGluIHJlc3VsdA0KXHgxYlsxbVx4MWJbMzFtRSAgICAgICBhc3NlcnQgJ0dPT0RfUFJPTVBUJyBpbiAiIyBCQURfUFJPTVBUIFxVMDAwMWY2YTlcXG5cXG5JdCBzZWVtcyBsaWtlIHlvdXIgcHJvbXB0IGlzIG1pc3Npbmcgc29tZSBlc3NlbnRpYWwgaW5mb3JtYXRpb24uIFRvIGNyZWF0ZSBhbiBlbmdhZ2luZyBzdG9yeSwgd2UgbmUuLi5lIHRoZXNlIGVzc2VudGlhbCBlbGVtZW50cywgYW5kIEknbGwgYmUgaGFwcHkgdG8gaGVscCB5b3UgY3JlYXRlIGEgY29tcGVsbGluZyBzdG9yeSBhYm91dCBDb29rZW5zaW8sIHRoZSBlbnRyZXByZW5ldXIhIlx4MWJbMG0NCg0KG1sxbRtbMzFtZXhlcmNpc2VzXDAyLXdyaXRlLXlvdXItZmlyc3QtcHJvbXB0LVx0ZXN0LnB5G1swbTo4MzogQXNzZXJ0aW9uRXJyb3INChtbMzZtG1sxbT09PT09PT09PT09PT09PT09PT09PT09PT09PSBzaG9ydCB0ZXN0IHN1bW1hcnkgaW5mbyA9PT09PT09PT09PT09PT09PT09PT09PT09PT0bWzBtDQpceDFiWzMxbUZBSUxFRFx4MWJbMG0gZXhlcmNpc2VzLzAyLXdyaXRlLXlvdXItZmlyc3QtcHJvbXB0LS90ZXN0LnB5OjpceDFiWzFtdGVzdF9wcm9tcHRceDFiWzBtIC0gYXNzZXJ0ICdHT09EX1BST01QVCcgaW4gIiMgQkFEX1BST01QVCBcVTAwMDFmNmE5XFxuXFxuSXQgc2VlbXMgbGlrZSB5b3VyIHByb21wdCBpcyBtaS4uLg0KG1szMW09PT09PT09PT09PT09PT09PT09PT09PT09IBtbMzFtG1sxbTEgZmFpbGVkG1swbSwgG1szMm0yIHBhc3NlZBtbMG0bWzMxbSBpbiAxLjg0cxtbMG0bWzMxbSA9PT09PT09PT09PT09PT09PT09PT09PT09G1swbQ0K",
                    "stderr": "G1sxbT09PT09PT09PT09PT09PT09PT09PT09PT09PT09IHRlc3Qgc2Vzc2lvbiBzdGFydHMgPT09PT09PT09PT09PT09PT09PT09PT09PT09PT0bWzBtDQpwbGF0Zm9ybSB3aW4zMiAtLSBQeXRob24gMy4xMS4zLCBweXRlc3QtOC4yLjIsIHBsdWdneS0xLjUuMA0Kcm9vdGRpcjogQzpcVXNlcnNcTEVHSU9OXFByb2plY3RzXGpvYnNcNGdlZWtzXHR1dG9yaWFsc1xwcm9tcHQtZW5nDQpwbHVnaW5zOiBhbnlpby00LjQuMCwgdGVzdGRveC0zLjEuMA0KY29sbGVjdGVkIDMgaXRlbXMNCg0KZXhlcmNpc2VzXDAyLXdyaXRlLXlvdXItZmlyc3QtcHJvbXB0LVx0ZXN0LnB5IBtbMzJtLhtbMG0bWzMybS4bWzBtG1szMW1GG1swbRtbMzFtICAgICAgICAgICAgICAgICAgICAgICAgWzEwMCVdG1swbQ0KDQo9PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09IEZBSUxVUkVTID09PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09DQobWzMxbRtbMW1fX19fX19fX19fX19fX19fX19fX19fX19fX19fX19fX18gdGVzdF9wcm9tcHQgX19fX19fX19fX19fX19fX19fX19fX19fX19fX19fX19fG1swbQ0KDQogICAgQHB5dGVzdC5tYXJrLml0KCJUaGUgcHJvbXB0IE1VU1QgaW5jbHVkZSBpbmZvcm1hdGlvbiBhYm91dCB0aGUgY2hhcmFjdGVycywgdGhlIHNjZW5lLCBhbmQgYXQgbGVhc3Qgb25lIG1vcmUgZWxlbWVudC4iKQ0KICAgIGRlZiB0ZXN0X3Byb21wdCgpOg0KICAgICAgICBQUk9NUFQgPSBvcGVuKHBhdGgsICJyIikucmVhZCgpDQogICAgICAgIHJlc3VsdCA9IGNyZWF0ZV9wcm9tcHQoVEVTVEVSX1BST01QVCwgUFJPTVBUKQ0KICAgIA0KICAgICAgICBpZiAiQkFEX1BST01QVCIgaW4gcmVzdWx0Og0KICAgICAgICAgICAgc2F2ZV9yZXBvcnQocmVzdWx0KQ0KICAgICAgICBlbHNlOg0KICAgICAgICAgICAgZGVsZXRlX3JlcG9ydCgpDQogICAgDQo+ICAgICAgIGFzc2VydCAiR09PRF9QUk9NUFQiIGluIHJlc3VsdA0KXHgxYlsxbVx4MWJbMzFtRSAgICAgICBhc3NlcnQgJ0dPT0RfUFJPTVBUJyBpbiAiIyBCQURfUFJPTVBUIFxVMDAwMWY2YTlcXG5cXG5JdCBzZWVtcyBsaWtlIHlvdXIgcHJvbXB0IGlzIG1pc3Npbmcgc29tZSBlc3NlbnRpYWwgaW5mb3JtYXRpb24uIFRvIGNyZWF0ZSBhbiBlbmdhZ2luZyBzdG9yeSwgd2UgbmUuLi5lIHRoZXNlIGVzc2VudGlhbCBlbGVtZW50cywgYW5kIEknbGwgYmUgaGFwcHkgdG8gaGVscCB5b3UgY3JlYXRlIGEgY29tcGVsbGluZyBzdG9yeSBhYm91dCBDb29rZW5zaW8sIHRoZSBlbnRyZXByZW5ldXIhIlx4MWJbMG0NCg0KG1sxbRtbMzFtZXhlcmNpc2VzXDAyLXdyaXRlLXlvdXItZmlyc3QtcHJvbXB0LVx0ZXN0LnB5G1swbTo4MzogQXNzZXJ0aW9uRXJyb3INChtbMzZtG1sxbT09PT09PT09PT09PT09PT09PT09PT09PT09PSBzaG9ydCB0ZXN0IHN1bW1hcnkgaW5mbyA9PT09PT09PT09PT09PT09PT09PT09PT09PT0bWzBtDQpceDFiWzMxbUZBSUxFRFx4MWJbMG0gZXhlcmNpc2VzLzAyLXdyaXRlLXlvdXItZmlyc3QtcHJvbXB0LS90ZXN0LnB5OjpceDFiWzFtdGVzdF9wcm9tcHRceDFiWzBtIC0gYXNzZXJ0ICdHT09EX1BST01QVCcgaW4gIiMgQkFEX1BST01QVCBcVTAwMDFmNmE5XFxuXFxuSXQgc2VlbXMgbGlrZSB5b3VyIHByb21wdCBpcyBtaS4uLg0KG1szMW09PT09PT09PT09PT09PT09PT09PT09PT09IBtbMzFtG1sxbTEgZmFpbGVkG1swbSwgG1szMm0yIHBhc3NlZBtbMG0bWzMxbSBpbiAxLjg0cxtbMG0bWzMxbSA9PT09PT09PT09PT09PT09PT09PT09PT09G1swbQ0KLAoKICAgCiAgICAgICAgICAbWzMxbVlvdXIgY29kZSBtdXN0IHRvIGNvbXBseSB3aXRoIHRoZSBmb2xsb3dpbmcgdGVzdHM6G1szOW0gCgogICAgIBtbMzFtG1sxbXggKGZhaWwpG1syMm0bWzM5bSAwLiAbWzM3bVRoZSBwcm9tcHQgTVVTVCBpbmNsdWRlIGluZm9ybWF0aW9uIGFib3V0IHRoZSBjaGFyYWN0ZXJzLCB0aGUgc2NlbmUsIGFuZCBhdCBsZWFzdCBvbmUgbW9yZSBlbGVtZW50LhtbMzltIAoK",
                    "exit_code": 1
                }
            ],
            "is_testeable": true,
            "opened_at": 1718211875020
        },
    ...rest of the files...
    ],
    "workout_session": [
        {
            "started_at": 1718211567826,
            "ended_at": 1718211913735
        },
        {
            "started_at": 1718211952333
        }
    ],
    "last_interaction_at": 1718211913735
}
```


Asegúrate de que tus URLs de transmisión y lote estén configuradas para recibir solicitudes POST. Está en tus manos idear la lógica que destilará los datos esenciales de estas interacciones.

¡Adéntrate en el mundo de la configuración de telemetría y eleva la experiencia educativa con LearnPack!
