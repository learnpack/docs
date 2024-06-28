---
title: 'Quickstart: How to install and start taking LearnPack tutorials'
description: "Kickstart your coding journey with LearnPack! Easily access tutorials via Codespaces, Gitpod, or locally with detailed guides."
tags: ['learnpack']
---

# Start Learning with LearnPack

 The following is a more detailed explanation on how to open LearnPack's tutorials locally or in the cloud:

## Pick the tutorial

You can learn many things with LearnPack: What do you want to learn? Our most popular tutorials help you learn [javascript arrays](https://4geeks.com/interactive-exercise/javascript-array-loops-exercises), [react js](https://4geeks.com/interactive-exercise/react-js-tutorial-exercises), how to [build API's with Python Flask](https://4geeks.com/interactive-coding-tutorial/python-flask-api-tutorial), etc. 

> 🛟 Here is a [curated list of our recommended tutorials](https://4geeks.com/lesson/learnpack-tutorial-database).

Each tutorial is a separate GitHub repository. Go to the GitHub repository website and read the README file to understand what the tutorial is about, you may find an `exercises` or .learn/exercises` with all the steps and instructions you will be given through the tutorial. We also have [this curate list of tutorials from 4Geeks Academy](https://4geeks.com/interactive-coding-tutorials) with a UI/UX that makes it a lot easier to pick.

## Run the tutorial

The easiest way to run a LearnPack tutorial is to initiate it using our [click-and-learn bridge](https://s.4geeks.com/start), if you will like to do it yourself (without any magic) read the following guide:

## How to open any LearnPack tutorial in the cloud (recommended)

> 🛟 Skip this section if you want to run locally on your computer

For this explanation, we picked the [Looping with Javascript](https://github.com/4GeeksAcademy/javascript-arrays-exercises-tutorial) tutorial.

### Opening on Github Codespaces

1. Open in Codespaces by clicking the repository **Code** button and then **Create codespace on master**
![Create Codespace](https://github.com/learnpack/docs/assets/107764250/982084dd-0053-4ab0-b6b8-d3b2c2037fc5)
2. When the Codespace finishes loading, it's ready!
3. Now you just have to start reading the instructions and doing the exercises.
![image](https://github.com/learnpack/docs/assets/107764250/d58a3831-b18a-4799-88be-75e9ed293254)

### Opening on Gitpod

1. Type the following URL on your browser:

```
https://gitpod.io/#<tutorial repository url>
```

Please note that `<tutorial repository url>` needs to be replaced with the github repository URL of the tutorial you want to open, for example: 

```
https://gitpod.io/#https://github.com/4GeeksAcademy/javascript-arrays-exercises-tutorial
```

> 🛟 Alternatively You can use the [Gitpod expension](https://www.gitpod.io/docs/configure/user-settings/browser-extension) that makes the process very similar to Codespaces by adding a button [like this](https://github.com/learnpack/docs/assets/107764250/366b2185-db53-4781-b304-b0b00cf635e3) into the repository website.

## How to download and run LearnPack tutorial in your local computer

To use LearnPack locally, you must install Node v20 (or more) and you may also have to install other things depending on the particular tutorial needs.

> 🛟 We recommend to install Node using NVM, here is a guide on [how to install NVM on your computer](https://4geeks.com/how-to/install-nvm-on-every-operating-system).

1. Once Node.js is installed, the next step is to install **LearnPack** using npm:

```node
npm i -g @learnpack/learnpack
```

2. Clone a LearnPack repository

Open the terminal and run the git clone command with your repository URL. For example, with the Javascript tutorial:

```git
git clone https://github.com/4GeeksAcademy/javascript-arrays-exercises-tutorial.git
```

3. Enter the new recently created directory

A directory with the name of the tutorial will be created; enter it with the cd command:

```cmd
cd javascript-arrays-exercises-tutorial
```

4. Start executing LearnPack
   
When you installed LearnPack globally, a new option was added to your computer's commands, now you can execute:

```learnpack
learnpack start
```

In the directory of a LearnPack tutorial, and you're done.

**Note**: If LearnPack detects that not installed plugins are needed for your tutorial, LearnPack will install them. Then just restart with **learnpack start**
![Needed plugins](https://github.com/learnpack/docs/assets/107764250/952ba5f4-5a7f-424e-8dfc-856f17f7a4b5)

### Use LearnPack locally with VSCode

Also, if you have VSCode on your computer, [install the Learnpack extension](https://marketplace.visualstudio.com/items?itemName=learn-pack.learnpack-vscode). Once you are inside a LearnPack tutorial in VSCode, if it is the first time you start, the LearnPack extension will execute **learnpack start** for you.
