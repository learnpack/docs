---
title: "Configure a LearnPack package to ask for delivery"
tags: ["learnpack"]
description: "LearnPack allows configuring project delivery as no delivery, file uploads (via MIME types), or URL submissions (validated by regex). Examples include PDFs, Word files, GitHub links, or Google Docs URLs."

---

# Configure LearnPack for delivering the package as a project

One of LearnPack's most popular features is the ability to ask students to deliver the package as homework. Here, you can configure a package to allow or not allow delivery.

## Projects with no delivery

```json filename="learn.json"
{
  "delivery": {
		"formats": ["no_delivery"]
	}
}
```

## Deliver a file

Before setting up your `learn.json`, you must know which mime types the learners will be able to upload to deliver the project successfully. If you have a sample file, I recommend you upload it to [mimetyp.io](https://mimetype.io/). To retrieve the particular string, you need to use a mime type.

![how to get mime types](https://github.com/learnpack/docs/blob/main/assets/mime-type.png?raw=true)

Once you get the mime type, you have to specify it under the delivery.formats array like this:

```json filename="learn.json"
{
	"delivery": {
		"formats": ["application/pdf"]
	}
}
```

The following are a few examples of different mime types:

### PDF file

```json filename="learn.json"
{
	"delivery": {
		"instructions": {
			"us": "Please drag your finished resume as a PDF file and upload it here",
			"es": "Porfavor adjunta tu resume/CV listo y como archivo PDF"
		},
		"formats": ["application/pdf"]
	}
}
```

### Text file with multiple mime possibilities

Sometimes, we want to allow multiple file types; in this case, the learner can upload a file from MS Word or PDF.

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

## Ask students to deliver a link

The default format to deliver a project using LearnPack is by specifying a github repository URL link with the following structure:

```url
https://github.com/<githun_username>/<github_repository>
```

But you can override that behavior by specifying a `regex` string like this:

```json filename="learn.json"
{
    "delivery": {
  		"formats": ["url"],
  		"regex": "https://github.com/"
    }
}
```

The following is a list of examples of different regex for different URL formats.

### URL from docs.google.com

```json filename="learn.json"
{
	"delivery": {
		"instructions": {
			"us": "Pase the URL of the Google Sheets template with the different strategies discussed during the game",
			"es": "Agrega el URL al document de Google Sheets con las diferentes strategies discutidas"
		},
		"formats": ["url"],
		"regex": "https://docs.google.com/"
	}
}
```

### URL from anywhere

Leave the `regex` key with `https://` only, and 4Geeks.com will ensure that the student specifies a URL from anywhere online.

```json filename="learn.json"
{
	"delivery": {
		"instructions": {
			"us": "Pase the URL of the Google Sheets template with the different strategies discussed during the game",
			"es": "Agrega el URL al document de Google Sheets con las diferentes strategies discutidas"
		},
		"formats": ["url"],
		"regex": "https://"
	}
}
```
