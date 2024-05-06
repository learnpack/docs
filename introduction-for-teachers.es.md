---
tags: ["LearnPack"]
authors: ["Charlytoc"]
description: "Enseñar con LearnPack es muy sencillo. En este artículo aprenderá cómo utilizar LearnPack para distribuir sus tutoriales"

---

# ¿Cómo enseñar con LearnPack?

LearnPack consta de varias aplicaciones conectadas entre sí, una CLI que te permite instalar plugins, iniciar los tutoriales o reiniciarlos por completo para eliminar archivos temporales. Además de una extensión para VSCode que te permite abrir una interfaz de React para que el estudiante lea las instrucciones, ejecute su código, hable con Rigobot AI y realice más acciones.

![LearnPack CLI](https://github.com/learnpack/docs/assets/107764250/7cf98dd0-6144-4b06-9543-aecaee3bb470)

Los cursos de LearnPack constan de distintos ejercicios que se guardan dentro de un directorio **exercises**. Aquí puedes ver un ejemplo:

![Example files](https://github.com/learnpack/docs/assets/107764250/eafb68d1-4dda-443c-8b69-6683069a0f1d)

### ¿Para qué sirve cada archivo?

- README.md: Son las instrucciones de cada uno de los ejercicios, en este caso en inglés por defecto. Puedes agregar más idiomas agregando la extensión del idioma, por ejemplo, para español: README.es.md
- app.js / app.py / index.html: Es el archivo principal que el estudiante deberá editar, puedes tener por defecto un contenido o empezar desde cero, depende de cómo quieras hacer el curso. LearnPack abrirá automáticamente este archivo cuando el estudiante esté en el ejercicio.
- test(s).js / test(s).py: Son los archivos para probar el código del estudiante, son opcionales, si el tutorial es de: Node, Dom, HTML o React, debes usar test.js, si es de Python, entonces usarás test.py. En el caso de Javascript, las pruebas son evaluadas usando Jest, en el caso de Python, con Pytest.
- solution.hide.html / solution.hide.js / solution.hide.css / solution.hide.py: Son archivos que contienen la solución al problema del ejercicio, es opcional, puedes incluirlo para asegurarte de que el estudiante pueda pasar el tutorial sin problemas.

Además, si agregas cualquier otro archivo, LearnPack también lo abrirá para el estudiante cuando esté en el ejercicio, siéntete libre de agregar todos los archivos necesarios para el ejercicio.
