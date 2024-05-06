---
description: "Explora la creación de tutoriales interactivos con LearnPack. Instala globalmente, inicia proyectos y personaliza ejercicios."

---

# Comenzando con LearnPack como Creador

Existen dos casos de uso que puedes aprovechar al usar LearnPack.

El primero es como [creador](#Creadores) de tutoriales interactivos, y el segundo caso de uso es como [aprendiz](#Aprendices), donde consumirás tutoriales interactivos creados por los creadores.
Encuentra LearnPack en npm, haz clic para descargar el paquete: [haz clic aquí](https://www.npmjs.com/package/@learnpack/learnpack).

> ✋ ¡Asegúrate de tener node instalado antes de pasar al siguiente paso!)

### Inicia tu primer tutorial

Para crear tu primer tutorial, debes seguir estos pasos:

1. Instala LearnPack globalmente en tu computadora ejecutando este comando (debes tener node instalado): `$ npm install @learnpack/learnpack -g`.  
2. Luego ejecuta este comando para comenzar a configurar tu tutorial: `$ learnpack init`.  
Este comando te preguntará todo sobre la configuración de tu tutorial, responde todas las preguntas y tu proyecto de tutorial será creado exitosamente. Estas son las preguntas que te hará:

Primero, te preguntará el tipo de calificación ([Tutoriales de Calificación](https://4geeks.com/docs/learnpack/grading-learnpack-tutorials)) que deseas para tu tutorial:

A) **Incremental**: En este tipo de ejercicio no puedes pasar al siguiente ejercicio hasta que apruebes la prueba del actual. Es incremental, por lo que los ejercicios posteriores requieren el conocimiento de los ejercicios anteriores.

B) **Isoolated**: Cada ejercicio es independiente por lo que puedes ir a cualquier ejercicio en el orden que prefieras. Los últimos ejercicios no necesitan el conocimiento de los ejercicios anteriores.

C) **No grading**: Estos ejercicios no están calificados, por lo tanto, no tienen pruebas.

![calificación de learnpack](https://raw.githubusercontent.com/learnpack/docs/main/assets/spaces_db2MUqxH83ZwH273KWpu_uploads_fAt71PHHbRLI1eiXNurN_Untitled%20(1).webp)
​​
4. A continuación, te preguntará por el título del tutorial.

![título del tutorial de learnpack](https://github.com/learnpack/docs/blob/main/assets/tutorial-title.png?raw=true)
​​
5. Después del título, debería preguntar por la descripción.

![Descripción](https://github.com/learnpack/docs/blob/main/assets/description-init.png)
​​

6. Luego te preguntará por la dificultad de los ejercicios del tutorial (Principiante, Fácil, Intermedio, Difícil).
​​![Dificultad](https://github.com/learnpack/docs/blob/main/assets/difficulty.png)

7. La siguiente pregunta será cuántas horas debería tomar completar el tutorial.
Puedes dejar esto como el número predeterminado (1) si aún no tienes claro cuánto tiempo durará el tutorial.
​​
Creará todos los archivos de tu tutorial y un nuevo directorio que los contiene.
Así es como debería verse tu proyecto:

![Archivos del directorio](https://github.com/learnpack/docs/blob/main/assets/initial-files.png)

​​
Ahora tienes que agregar la carpeta de cada uno de los ejercicios que vas a añadir a tu tutorial con una estructura similar a la creada por el comando `$ learnpack init`.

Debería tener el archivo `README.md`, el archivo `test` y el archivo de entrada (generalmente llamado `app.<ext>` donde la extensión (`ext`) depende del lenguaje de aprendizaje. Por ejemplo, si estamos construyendo un tutorial de Python, será `app.py` (este nombre puede ser modificado en las opciones de configuración).

Los últimos dos archivos dependen del lenguaje que estés utilizando.

[Aquí](#aún-no-disponible) hay una explicación detallada de cada archivo.
