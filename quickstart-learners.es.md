---
title: 'Paso a paso: Cómo instalar y comenzar con los tutoriales de LearnPack'
description: "¡Inicia tu viaje de codificación paso a paso con LearnPack! Accede fácilmente a los tutoriales a través de Codespaces, Gitpod o localmente con guías detalladas."
tags: ['learnpack']

---

# Comienza a Aprender con LearnPack

La siguiente es una explicación más detallada sobre cómo abrir los tutoriales de LearnPack localmente o en la nube:

## Elige el tutorial

Puedes aprender muchas cosas con LearnPack: ¿Qué quieres aprender? Nuestros tutoriales más populares te ayudan a aprender [arrays en JavaScript](https://4geeks.com/interactive-exercise/javascript-array-loops-exercises), [React.js](https://4geeks.com/interactive-exercise/react-js-tutorial-exercises), cómo [construir APIs con Python Flask](https://4geeks.com/interactive-coding-tutorial/python-flask-api-tutorial), etc.

> 🛟 Aquí tienes una [lista seleccionada de nuestros tutoriales recomendados](https://4geeks.com/lesson/learnpack-tutorial-database).

Cada tutorial es un repositorio separado en GitHub. Ve al sitio web del repositorio de GitHub y lee el archivo README para entender de qué trata el tutorial. Puedes encontrar un `exercises` o `.learn/exercises` con todos los pasos e instrucciones que recibirás durante el tutorial. También tenemos [esta lista seleccionada de tutoriales de 4Geeks Academy](https://4geeks.com/interactive-coding-tutorials) con una interfaz que facilita la elección.

## Ejecuta el tutorial

La forma más fácil de ejecutar un tutorial de LearnPack es iniciarlo utilizando nuestro [puente de clic y aprende](https://s.4geeks.com/start), si prefieres hacerlo tú mismo (sin magia), lee la siguiente guía:

## Cómo abrir cualquier tutorial de LearnPack en la nube (recomendado)

> 🛟 Omite esta sección si deseas ejecutarlo localmente en tu computadora

Para esta explicación, elegimos el tutorial [Loops en JavaScript](https://github.com/4GeeksAcademy/javascript-arrays-exercises-tutorial).

### Abrir en Github Codespaces

1. Ábrelo en Codespaces haciendo clic en el botón **Code** del repositorio y luego en **Create codespace on master**
![Create Codespace](https://github.com/learnpack/docs/assets/107764250/982084dd-0053-4ab0-b6b8-d3b2c2037fc5)
2. Cuando Codespace termine de cargarse, ¡estará listo!
3. Ahora solo tienes que comenzar a leer las instrucciones y hacer los ejercicios.
![image](https://github.com/learnpack/docs/assets/107764250/d58a3831-b18a-4799-88be-75e9ed293254)

### Abrir en Gitpod

1. Escribe la siguiente URL en tu navegador:

```url
https://gitpod.io/#<tutorial repository url>
```

Ten en cuenta que `<tutorial repository url>` debe ser reemplazado con la URL del repositorio de GitHub del tutorial que deseas abrir, por ejemplo:

```url
https://gitpod.io/#https://github.com/4GeeksAcademy/javascript-arrays-exercises-tutorial
```

> 🛟 Alternativamente, puedes usar la [extensión de Gitpod](https://www.gitpod.io/docs/configure/user-settings/browser-extension) que hace el proceso muy similar a Codespaces al agregar un botón [como este](https://github.com/learnpack/docs/assets/107764250/366b2185-db53-4781-b304-b0b00cf635e3) en el sitio web del repositorio.

## Cómo descargar y ejecutar un tutorial de LearnPack en tu computadora local

Para usar LearnPack localmente, debes instalar Node v20 (o superior) y también es posible que necesites instalar otras cosas según las necesidades particulares del tutorial.

> 🛟 Recomendamos instalar Node usando NVM, aquí tienes una guía sobre [cómo instalar NVM en tu computadora](https://4geeks.com/how-to/install-nvm-on-every-operating-system).

1. Una vez instalado Node.js, el siguiente paso es instalar **LearnPack** usando npm:

```bash
npm i -g @learnpack/learnpack
```

2. Clona un repositorio de LearnPack

Abre la terminal y ejecuta el comando git clone con la URL de tu repositorio. Por ejemplo, con el tutorial de JavaScript:

```bash
git clone https://github.com/4GeeksAcademy/javascript-arrays-exercises-tutorial.git
```

3. Entra en el nuevo directorio recién creado

Se creará un directorio con el nombre del tutorial; entra en él con el comando cd:

```bash
cd javascript-arrays-exercises-tutorial
```

4. Comienza a ejecutar LearnPack
   
Cuando instalaste LearnPack globalmente, se agregó una nueva opción a los comandos de tu computadora, ahora puedes ejecutar:

```bash
learnpack start
```

En el directorio de un tutorial de LearnPack, y ya está.

**Nota**: Si LearnPack detecta que se necesitan plugins no instalados para tu tutorial, LearnPack los instalará. Luego solo reinicia con **learnpack start**
![Needed plugins](https://github.com/learnpack/docs/assets/107764250/952ba5f4-5a7f-424e-8dfc-856f17f7a4b5)

### Usar LearnPack localmente con VSCode

Además, si tienes VSCode en tu computadora, [instala la extensión Learnpack](https://marketplace.visualstudio.com/items?itemName=learn-pack.learnpack-vscode). Una vez que estés dentro de un tutorial de LearnPack en VSCode, si es la primera vez que inicias, la extensión de LearnPack ejecutará **learnpack start** por ti.
