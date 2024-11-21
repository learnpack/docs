---
title: "Configurar un paquete de LearnPack para solicitar entrega"
tags: ["learnpack"]
description: "LearnPack permite configurar la entrega de proyectos como sin entrega, carga de archivos (a través de tipos MIME) o envío de URLs (validadas con regex). Ejemplos incluyen archivos PDF, documentos Word, enlaces de GitHub o Google Docs."

---

# Configurar LearnPack para entregar el paquete como un proyecto

Una de las funciones más populares de LearnPack es la capacidad de pedir a los estudiantes que entreguen el paquete como tarea. Aquí puedes configurar un paquete para permitir o no permitir entregas.

## Proyectos sin entrega

```json filename="learn.json"
{
  "delivery": {
		"formats": ["no_delivery"]
	}
}
```

## Entregar un archivo

Antes de configurar tu `learn.json`, debes conocer qué tipos MIME podrán subir los estudiantes para entregar el proyecto con éxito. Si tienes un archivo de muestra, te recomiendo subirlo a [mimetyp.io](https://mimetype.io/) para obtener la cadena específica que necesitas usar.

![cómo obtener tipos MIME](https://github.com/learnpack/docs/blob/main/assets/mime-type.png?raw=true)

Una vez que tengas el tipo MIME, debes especificarlo en el array `delivery.formats` como este ejemplo:

```json filename="learn.json"
{
	"delivery": {
		"formats": ["application/pdf"]
	}
}
```

A continuación, algunos ejemplos de diferentes tipos MIME:

### Archivo PDF

```json filename="learn.json"
{
	"delivery": {
		"instructions": {
			"us": "Please drag your finished resume as a PDF file and upload it here",
			"es": "Por favor adjunta tu currículum listo como un archivo PDF"
		},
		"formats": ["application/pdf"]
	}
}
```

### Archivo de texto con múltiples posibilidades MIME

A veces, queremos permitir múltiples tipos de archivo; en este caso, el estudiante puede subir un archivo de MS Word o PDF.

```json filename="learn.json"
{
	"delivery": {
		"instructions": {
			"us": "Create a text document with the answers to the questions in the instructions",
			"es": "Adjunta un documento con las respuestas a las preguntas"
		},
		"formats": ["application/msword,application/vnd.openxmlformats-officedocument.wordprocessingml.document,application/pdf"]
	}
}
```

## Solicitar a los estudiantes entregar un enlace

El formato predeterminado para entregar un proyecto usando LearnPack es especificando un enlace de un repositorio de GitHub con la siguiente estructura:

```url
https://github.com/<githun_username>/<github_repository>
```

Pero puedes sobrescribir este comportamiento especificando una cadena `regex` como esta:

```json filename="learn.json"
{
    "delivery": {
  		"formats": ["url"],
  		"regex": "https://github.com/"
    }
}
```

A continuación, una lista de ejemplos de diferentes regex para formatos de URL:

### URL de docs.google.com

```json filename="learn.json"
{
	"delivery": {
		"instructions": {
			"us": "Paste the URL of the Google Sheets template with the different strategies discussed during the game",
			"es": "Agrega la URL del documento de Google Sheets con las diferentes estrategias discutidas"
		},
		"formats": ["url"],
		"regex": "https://docs.google.com/"
	}
}
```

### URL desde cualquier lugar

Deja la clave `regex` con solo `https://` y 4Geeks.com se asegurará de que el estudiante especifique una URL desde cualquier lugar en línea.

```json filename="learn.json"
{
	"delivery": {
		"instructions": {
			"us": "Paste the URL of the Google Sheets template with the different strategies discussed during the game",
			"es": "Agrega la URL del documento de Google Sheets con las diferentes estrategias discutidas"
		},
		"formats": ["url"],
		"regex": "https://"
	}
}
```
