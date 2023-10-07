# LearnPack Configuration

## The learn.json

The `learn.json` file is where all the configurations from the teacher should be set. These are the properties that you can change from the configuration:

*   `port`: The port where the instructions will be hosted. (Default: 3000).
    

*   `editor`: Editor will be the object with all the editor options, which are the following:
    
    *   `mode`: The mode could be `vscode` (when using the vscode plugin) or standalone (When working locally without vscode).
        
    
    *   `agent`: The agent is where you are going to show the instructions, it could be `localhost`, `gitpod` or `vscode`.
        
    
    *   `version`: This is related to the UI version, by default, it will use the newest version of the UI, anyway you can use an older version.
        

*   `dirPath`: The path to the configuration directory, by default this directory will be named “.learn” and will be located at the root of the project.
    

*   `configPath`: The path to the configuration file, this file will be named learn.json by default.
    

*   `outputPath`: The path to the folder where the output of the exercises will be located. It will be `.learn/dist` by default.
    

*   `publicPath`: The path of the domain where the result will be hosted. Its value will be `/preview` by default.
    

*   `publicUrl`: The URL where the instructions will be hosted, its value depends on the agent that you are using.
    

*   `language`: The programming language used in the tutorial. It could be set to auto if you are using many programming languages, LearnPack will auto-detect the language.
    

*   `grading`: The grading mode of the tutorial. You can see more about grading modes here: [Grading Modes](/grading-tutorials)​
    

*   `exercisesPath`: The path to the folder where the exercises are located. They could be located at the root of the project.
    

*   `disabeldActions`: This will be an array with the actions that you would like to disable, i.e.: You can disable the option of having a test on your tutorial while you fix a bug. You can disable the following actions: Build, Reset, Test and Tutorial.
    

*   `slug`: The name of the tutorial. It is automatically created when you create the tutorial, but you can also change it later.
    

*   `title`: The title of the tutorial.
    

*   `preview`: It’s an image that can be used for the introduction of your exercises.
    

*   `repository`: The link where the repository of the tutorial is hosted.
    

*   `description`: The description of the tutorial.
    

*   `intro`: Here you can add the link to an introductory video that you can show before the first exercise.
    

*   `duration`: The estimated time that it should take you to finish the tutorial.
    

*   `difficulty`: The difficulty of the tutorial.
    

*   `autoStart`: It will allow you to decide if LearnPack should start automatically when opening the repository at vscode.
    

> 😳 Disclaimer: The next features are still a work in progress! Bear with us while we still develop them for you.

*   `bugs`: Add a link where the learners can report bugs found in your tutorial.
    
*   `webpackTemplate`: It will allow creators to have their own webpack template.
     

## Compiler Plugins

LearnPack has some plugins that allow you to compile and test tutorials in different languages. The languages covered by LearnPack so far are: python, javascript, html, css, dom, react.

These are the plugins for the named languages:

*   `@learnpack/html`
    

*   `@learnpack/node`
    

*   `@learnpack/python`
    

*   `@learnpack/dom`
    

*   `@learnpack/react`
    

PS: When using one of these languages with LearnPack, you have to install the corresponding plugin to compile and test the exercises. This is how you install the plugins:

```bash
$ learnpack plugins:install <name-of-plugin>
```

For example, let's install `@learnpack/html`:

```bash
learnpack plugins:install @learnpack/html
```

### Flags

We are still working to add the new version with the flags. They will allow you to run the command with special behavior.

### Gitpod Integration

​[Gitpod](https://www.gitpod.io/) is an amazing tool that can help your tutorial’s user experience by allowing a very simple way to use Learnpack.

Using Gitpod on your tutorial will allow the learners to access and start the tutorials only by clicking once.

![](https://github.com/learnpack/docs/blob/main/assets/gitpod.gif?raw=true)
