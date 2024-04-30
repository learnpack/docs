# Configuración de LearnPack

### El archivo learn.json

El archivo `learn.json` es donde se establecen todas las configuraciones del instructor. Estas son las propiedades que puedes cambiar en la configuración:

* `port`: El puerto donde se alojarán las instrucciones. (Por defecto: 3000).

* `editor`: El editor será el objeto con todas las opciones del editor, que son las siguientes:
    * `mode`: El modo puede ser `extension` (cuando se usa el complemento de vscode) o `preview` (cuando se trabaja localmente sin vscode).
    * `agent`: El agente es donde se mostrarán las instrucciones, puede ser `vscode`, `os`.
    * `version`: Esto está relacionado con la versión de la interfaz de usuario, por defecto, se usará la versión más nueva de la interfaz de usuario, de todos modos, puedes usar una versión anterior.

* `dirPath`: La ruta al directorio de configuración, por defecto este directorio se llamará “.learn” y estará ubicado en la raíz del proyecto.

* `configPath`: La ruta al archivo de configuración, este archivo se llamará learn.json por defecto.

* `outputPath`: La ruta a la carpeta donde se ubicará la salida de los ejercicios. Será `.learn/dist` por defecto.

* `publicPath`: La ruta del dominio donde se alojará el resultado. Su valor será `/preview` por defecto.

* `publicUrl`: La URL donde se alojarán las instrucciones, su valor depende del agente que estés usando.

* `language`: El lenguaje de programación utilizado en el tutorial. Se puede configurar en auto si estás usando varios lenguajes de programación, LearnPack detectará automáticamente el lenguaje.

* `grading`: El modo de calificación del tutorial. Puedes ver más sobre los modos de calificación aquí: [Modos de Calificación](/grading-tutorials).

* `exercisesPath`: La ruta a la carpeta donde se encuentran los ejercicios. Podrían estar ubicados en la raíz del proyecto.

* `disabledActions`: Será un arreglo con las acciones que te gustaría deshabilitar, es decir: Puedes deshabilitar la opción de tener una prueba en tu tutorial mientras arreglas un error. Puedes deshabilitar las siguientes acciones: Build, Reset, Test y Tutorial.

* `slug`: El nombre del tutorial. Se crea automáticamente cuando creas el tutorial, pero también puedes cambiarlo más tarde.

* `title`: El título del tutorial.

* `preview`: Es una URL de imagen que se puede usar para la introducción de tus ejercicios.

* `repository`: El enlace donde se aloja el repositorio del tutorial.

* `description`: La descripción del tutorial.

* `duration`: El tiempo estimado que debería llevarte terminar el tutorial.

* `difficulty`: La dificultad del tutorial.

* `autoStart`: Te permitirá decidir si LearnPack debería comenzar automáticamente al abrir el repositorio en vscode.

* `video`: Un objeto que contiene una propiedad `intro`, que es un objeto que tiene como claves los idiomas y como valores una URL para un video introductorio del tutorial en cada idioma que desees. Por ejemplo:
  ```json
  "video": {
      "intro": {
          "es": "www.ejemplo.url",
          "en": "www.ejemplo_video.url"
      }
  }
  ```

* `bugs`: Añade un enlace donde los alumnos pueden reportar errores encontrados en tu tutorial.

* `webpackTemplate`: Permitirá a los creadores tener su propia plantilla de webpack.

### Plugins de Compilador

LearnPack tiene algunos plugins que te permiten compilar y probar tutoriales en diferentes lenguajes. Los lenguajes cubiertos por LearnPack hasta ahora son: python, javascript, html, css, dom, react.

Estos son los plugins para los lenguajes mencionados:

* `@learnpack/html`
* `@learnpack/node`
* `@learnpack/python`
* `@learnpack/dom`
* `@learnpack/react`

PS: Cuando uses uno de estos lenguajes con LearnPack, tienes que instalar el plugin correspondiente para compilar y probar los ejercicios. Así es como instalas los plugins:

```bash
$ learnpack plugins:install <nombre-del-plugin>
```

Por ejemplo, vamos a instalar `@learnpack/html`:

```bash
learnpack plugins:install @learnpack/html
```

Pero actualmente LearnPack es capaz de instalar el plugin por sí mismo basado en los ejercicios que has agregado.

### Integración con Gitpod

[Gitpod](https://www.gitpod.io/) es una herramienta increíble que puede ayudar a la experiencia del usuario de tu tutorial al permitir una forma muy simple de usar LearnPack.

Usar Gitpod en tu tutorial permitirá a los alumnos acceder y comenzar los tutoriales solo con hacer clic una vez.

![](https://github.com/learnpack/docs/blob/main/assets/gitpod.gif?raw=true)

### Integración con Codespaces

[Codespaces](https://github.visualstudio.com/features/codespaces/) proporciona un entorno de desarrollo en la nube potente, personalizable y escalable. LearnPack puede funcionar sin problemas dentro de un Codespace, permitiendo a los alumnos acceder y comenzar tutoriales con una configuración mínima. Esta integración asegura que todas las dependencias y herramientas necesarias estén preconfiguradas, haciendo el proceso de aprendizaje suave y eficiente.

Al aprovechar Codespaces, los usuarios pueden disfrutar de un entorno de desarrollo completamente equipado directamente en su navegador, lo cual es especialmente beneficioso para tutoriales que requieren configuraciones específicas o cadenas de herramientas extensas. Esta integración simplifica el proceso de configuración inicial, reduce errores potenciales y permite a los alumnos concentrarse más en aprender en lugar de configurar su entorno de desarrollo.

Esta es un ejemplo de configuración de codespaces:

.devcontainer/devcontainers.json
```json
{
	"name": "Node.js",
	"image": "mcr.microsoft.com/devcontainers/javascript-node:0-18",
	"customizations": {
		"vscode": {
			"settings": {
				"editor.defaultFormatter": "esbenp.prettier-vscode",
				"workbench.editorAssociations": {   
					"*.md": "vscode.markdown.preview.editor"
				}
			},
			"extensions": ["learn-pack.learnpack-vscode"]
		}
	},

	"onCreateCommand": "npm i jest@24.8.0 -g && npm i @learnpack/learnpack@2.1.39 -g && learnpack plugins:install @learnpack/node@1.1.5 && learnpack plugins:install @learnpack/html@1.1.2"
}
```
