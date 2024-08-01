---
tags: ["learnpack"] 
title: "Soluciones y preguntas frecuentes"
---

LearnPack es un producto en el que se han invertido muchas horas de trabajo, es por eso que para tener una mejor experiencia de usuario, aquí están recopiladas algunas de las preguntas más frecuentas sobre la interfaz y errores comunes.

## Preguntas frecuentes
### ¿Cómo abro las instrucciones a la derecha?
Para abrir la interfaz de LearnPack tienes varias maneras: 
- Reiniciar LearnPack
  1. Presiona `Ctrl` + `C` para detener LearnPack
  2. Ejecuta nuevamente `learnpack start`

Si tienes instalada la [extensión de LearnPack](https://marketplace.visualstudio.com/items?itemName=learn-pack.learnpack-vscode) en tu editor de código, las instrucciones deberían abrir automáticamente.

- Usando la `paleta de comandos` del editor:
  1. Presiona `F1` o `Ctrl` + `Shift` + `P` 
  2. Escribe `LearnPack`
  3. Selecciona la opción `LearnPack: Open Instructions`



### No veo la terminal
Para abrir la terminal generalmente puedes hacer cualquiera de las siguientes:

1. Usar el atajo de teclado `Ctrl` + `J` en tu editor de código
2. Usar el atajo de teclado `Ctrl` + ` (backtick) en tu editor
3. **Comando Rápido**: Presiona `Ctrl` + `Shift` + `P` para abrir la paleta de comandos, luego escribe `Terminal: Crear nueva terminal` y selecciona la opción.

### ¿Cómo abrir una segunda terminal?
Si estás usando VSCode, puedes abrir una segunda terminal de las siguientes maneras:

1. **Usando el menú**:
   - Ve a la barra de menú y selecciona `Terminal`.
   - Luego selecciona `Nueva Terminal`.

2. **Usando atajos de teclado**:
   - Presiona `Ctrl` + `Shift` + ` (backtick) para abrir una nueva terminal.

3. **Usando la paleta de comandos**:
   - Presiona `F1` o `Ctrl` + `Shift` + `P` para abrir la paleta de comandos.
   - Escribe `Terminal: Crear nueva terminal` y selecciona la opción.

Estas opciones te permitirán abrir una segunda terminal en tu editor de código VSCode.



### ¡Conexión perdida!
El error de conexión perdida sucede cuando la interfaz de LearnPack no se puede comunicar con el servidor de LearnPack corriendo en tu máquina. Para resolverlo, debería bastar con asegurarse de que LearnPack esté corriendo en una terminal. 

- Si no está corriendo, ejecutar: `learnpack start` y esperar un par de segundo a que la interfaz reconecte automáticamente.
- En caso de que LearnPack ya esté corriendo simplemente presina el botón de `Recargar` que la modal de conexión perdida te muestra.


### 'learnpack' is not recognized as an internal or external command
> This message may be different depending of your operating system.

If LearnPack is not installed in your system, the command `learnpack start` and any `learnpack` command won't work. To solve this issue, just install LearnPack in your system with the following command: `npm i -g @learnpack/learnpack`. This will install the latest version of LearnPack from npm registry globally in your system.

```text
To execute learnPack locally, you must have Node (> 14) installed.
```
> 💡 You can check if LearnPack is installed with the following command: 
`npm ls -g @learnpack/learnpack`