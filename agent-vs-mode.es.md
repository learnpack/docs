---
tags: ["learnpack"] 
title: "Agent y Mode en LearnPack"
authors: ["Charlytoc"]
---

## Qué es el Agent en LearnPack
LearnPack es una aplicación con distintas pequeñas partes conectadas entre sí. Cuando ejecutas LearnPack dentro de Visual Studio Code es ligeramente distinto a hacerlo desde un navegador. Debido a estas diferencias de implementación, es posible configurar LearnPack para que abra como una extensión de VSCode (agent = "vscode") o para que abra la interfaz en el navegador (agent = "os").

## Qué es el "mode" en LearnPack
LearnPack va a notar en qué programa se ejecutó para determinar el agent, pero además el agent puede especificarse dentro de `learn.json` en la sección `editor.agent`. Esto permite a los usuarios definir explícitamente cómo desean que se ejecute LearnPack.

Si se detecta una diferencia entre el agent detectado y el sugerido, LearnPack mostrará un aviso. Este aviso es importante para asegurar que la experiencia de usuario sea la mejor posible, ya que cada agent tiene sus propias características y ventajas.

Por ejemplo, si LearnPack detecta que se está ejecutando en VSCode pero el archivo `learn.json` sugiere que debería ejecutarse en un navegador, se mostrará un mensaje recomendando cambiar el agent para evitar posibles problemas de compatibilidad o funcionalidad.

## Cómo correr LearnPack dentro de agent "os"
Para correr LearnPack como agent "os", sigue estos pasos:

1. **Cerrar VSCode**:
   - Guarda tu trabajo y cierra la aplicación de VSCode.

2. **Abrir una nueva terminal**:
   - Abre una terminal o símbolo del sistema en tu sistema operativo.

3. **Navegar al directorio de tu proyecto LearnPack**:
   - Usa el comando `cd` para navegar al directorio donde se encuentra tu proyecto LearnPack.

4. **Ejecutar LearnPack**:
   - Ejecuta el siguiente comando para iniciar LearnPack:
     ```sh
     learnpack start
     ```

## Cómo correr LearnPack desde VSCode
Para correr LearnPack como una extensión de VSCode, sigue estos pasos:

1. **Abrir VSCode**:
   - Lanza la aplicación Visual Studio Code en tu computadora.

2. **Instalar la extensión LearnPack**:
   - Ve a la vista de Extensiones haciendo clic en el ícono de Extensiones en la Barra de Actividades en el lado de la ventana o presionando `Ctrl+Shift+X`.
   - Busca "LearnPack" y haz clic en "Instalar".
   - Si la extensión ya está instalada pero deshabilitada, habilítala.

3. **Abrir tu terminal en VSCode**:
   - Abre tu terminal en VSCode.

4. **Navegar al directorio de tu proyecto LearnPack**:
   - Usa el comando `cd` para navegar al directorio donde se encuentra tu proyecto LearnPack.

5. **Ejecutar LearnPack**:
   - Ejecuta el siguiente comando para iniciar LearnPack:
     ```sh
     learnpack start
     ```

