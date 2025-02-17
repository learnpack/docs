---
tags: ["learnpack"]
title: "Cómo publicar un paquete LearnPack en la nube"
description: "LearnPack ha evolucionado. Ahora puedes publicar tus paquetes en la nube, para que puedas acceder a ellos desde cualquier lugar, en cualquier dispositivo. Durante esta guía aprenderás cómo publicar tus propios paquetes LearnPack y comenzar a compartirlos con tus amigos, colegas, estudiantes y el mundo entero."
---

# Requisitos previos

- Debes tener una cuenta de 4Geeks. Si no tienes una, puedes crearla [aquí](https://4geeks.com/pricing).
- Una vez que hayas creado una cuenta, necesitas aceptar la invitación de Rigobot en tu panel de control.
  ![Rigobot conectado](https://raw.githubusercontent.com/learnpack/docs/373d979448fdb782ea499e8f8c19caae2730759d/assets/rigobot-connected.png)
- Debes tener un permiso de _Publisher_ en tu panel de control de 4Geeks. Si no lo tienes, puedes solicitarlo contactando al soporte.

# Publicando un paquete

1. Abre tu paquete LearnPack en tu entorno preferido, Gitpod, Codespaces o localmente.

2. Verifica que tienes la última versión de LearnPack instalada ejecutando `learnpack --version` en tu terminal. Todas las versiones superiores a la 4.0.17 son compatibles. Si no tienes la última versión, puedes actualizar LearnPack ejecutando `npm i -g @learnpack/learnpack`.

3. Revisa el archivo `learn.json` para asegurarte de que la `editor.version` tenga una versión igual o superior a _5.0_. Esto asegurará que tu paquete sea compatible con el último editor de LearnPack, incluyendo las nuevas características y mejoras como **Iniciar sesión con GitHub**, **Gestión de sesiones** y el nuevo **Modo oscuro**.
   ![learnpack-editor learn.json](https://raw.githubusercontent.com/learnpack/docs/373d979448fdb782ea499e8f8c19caae2730759d/assets/learnpack-editor.png)
4. Ejecuta `learnpack publish` en tu terminal.

5. Sigue las instrucciones en la terminal para publicar tu paquete.

6. ¡Listo! Tu paquete ahora está publicado y puedes compartirlo con cualquiera.
