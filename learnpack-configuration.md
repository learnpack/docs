# LearnPack Configuration

## The learn.json

The `learn.json` file is where all the configurations from the teacher should be set. These are the properties that you can change from the configuration:

<!-- Note: The properties marked with ? are optional, LearnPack is able to figure it out by itself based on the exercises of the tutorial.-->

*   `port`: The port where the instructions will be hosted. (Default: 3000).

*   `editor`: Editor will be the object with all the editor options, which are the following:
    
    *   `mode`: The mode could be `extension` (when using the vscode plugin) or `preview` (When working locally without vscode).
    
    *   `agent`: The agent is where you are going to show the instructions, it could be `vscode`, `os`.
    *   `version`: This is related to the UI version, by default, it will use the newest version of the UI, anyway you can use an older version.
        

*   `dirPath`: The path to the configuration directory, by default this directory will be named “.learn” and will be located at the root of the project.
    
*   `configPath`: The path to the configuration file, this file will be named learn.json by default.
    
*   `outputPath`: The path to the folder where the output of the exercises will be located. It will be `.learn/dist` by default.
    

*   `publicPath`: The path of the domain where the result will be hosted. Its value will be `/preview` by default.
    

*   `publicUrl`: The URL where the instructions will be hosted, its value depends on the agent that you are using.
    

*   `language`: The programming language used in the tutorial. It could be set to auto if you are using many programming languages, LearnPack will auto-detect the language.
    
*   `grading`: The grading mode of the tutorial. You can see more about grading modes here: [Grading Modes](/grading-tutorials)​
    

*   `exercisesPath`: The path to the folder where the exercises are located. They could be located at the root of the project.
    

*   `disabledActions`: This will be an array with the actions that you would like to disable, i.e.: You can disable the option of having a test on your tutorial while you fix a bug. You can disable the following actions: Build, Reset, Test and Tutorial.
    

*   `slug`: The name of the tutorial. It is automatically created when you create the tutorial, but you can also change it later.
    

*   `title`: The title of the tutorial.
    
*   `preview`: It’s an image url that can be used for the introduction of your exercises.

*   `repository`: The link where the repository of the tutorial is hosted.
    

*   `description`: The description of the tutorial.
    

<!--*   `intro`: Here you can add the link to an introductory video that you can show before the first exercise.
     -->

*   `duration`: The estimated time that it should take you to finish the tutorial.
    

*   `difficulty`: The difficulty of the tutorial.
    

*   `autoStart`: It will allow you to decide if LearnPack should start automatically when opening the repository at vscode.

* `video`: An object containing a property `intro`, that is an object that has as keys languages and as values an url for an intro video for the tutorial in each language you want. For example: 
```json
"video": {
    "intro": {
        "es": "www.example.url",
        "en": "www.example_video.url"
    }
}
```

> 😳 Disclaimer: The next features are still a work in progress! Bear with us while we still develop them for you.

*   `bugs`: Add a link where the learners can report bugs found in your tutorial.
    
*   `webpackTemplate`: It will allow creators to have their Webpack template.

*   `delivery`: It allows for enforcing a specific delivery method for learners to use when delivering the completed tutorial solution. For example:

```json
"delivery": {
	"instructions": {
		"us": "Pase the URL of the Google Sheets template with the different strategies discussed during the game",
		"es": "Agrega el URL al document de Google Sheets con las diferentes strategies discutidas"
	},
	"formats": ["url"],
	"regex": "https://docs.google.com/"
}
```

## Compiler Plugins

LearnPack has some plugins that allow you to compile and test tutorials in different languages. The languages covered by LearnPack so far are: python, javascript, html, css, dom, react.

These are the plugins for the named languages:

*   [@learnpack/html](https://4geeks.com/docs/learnpack/building-html-css-tutorials): Very simple setup for HTML and CSS grading and compilation.
    

*   [@learnpack/node](https://4geeks.com/docs/learnpack/building-javascript-tutorials): For purely javascript and node.js tutorials.
    

*   [@learnpack/python](https://4geeks.com/docs/learnpack/building-python-tutorials): Python 3 compiler with pyUnit integration for testing.
    

*   [@learnpack/dom](https://4geeks.com/docs/learnpack/building-dom-tutorials): It uses WebPack to compile each tutorial as a website and jest for DOM testing.
    

*   [@learnpack/react](https://4geeks.com/docs/learnpack/building-react-tutorials): It uses WebPack to build your tutorials for react 18 and jest for exercise testing.
    

PS: When using one of these languages with LearnPack, you have to install the corresponding plugin to compile and test the exercises. This is how you install the plugins:

```bash
$ learnpack plugins:install <name-of-plugin>
```

For example, let's install `@learnpack/html`:

```bash
learnpack plugins:install @learnpack/html
```

But currently LearnPack is able to install the plugin by itself based on the exercises you've added. 👀


<!-- No need to tell unfinished features
### Flags

We are still working to add the new version with the flags. They will allow you to run the command with special behavior.
 -->

## Cloud Provisioning

As a design decision; LearnPack doesn't handle any technology installation or setup for your tutorials.

It's a great idea to use cloud provisioning vendors like Gitpod or Github Codespaces to remove setup and tech installation from the user and greatly reduce learning friction. Provisioning vendors can automate every step of the tutorial's technology needs in a matter of seconds and LearnPack will start immediately after the environment is ready:

### Provisioning LearnPack with Gitpod

​[Gitpod](https://www.gitpod.io/) asks for a `[./gitpod.yml](https://www.gitpod.io/docs/references/gitpod-yml)` file to be added at the root of the repository. Gitpod allows you to specify a Docker image, python version and anything you need for your LearnPack tutorial to run smoothly.

Using Gitpod on your tutorial will allow the learners to access and start the tutorials only by clicking once.

![](https://github.com/learnpack/docs/blob/main/assets/gitpod.gif?raw=true)

### Provisioning LearnPack with Github Codespaces

[Codespaces](https://github.visualstudio.com/features/codespaces/) provides a powerful, customizable, and scalable cloud development environment. LearnPack can run seamlessly within a Codespace, allowing learners to access and start tutorials with minimal setup. This integration ensures that all necessary dependencies and tools are pre-configured, making the learning process smooth and efficient.

By leveraging Codespaces, users can enjoy a fully featured development environment directly in their browser, which is especially beneficial for tutorials that require specific configurations or extensive toolchains. This integration simplifies the initial setup process, reduces potential errors, and allows learners to focus more on learning rather than configuring their development environment.

This is an example codespaces configuration:

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
