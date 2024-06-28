---
description: "Explore interactive tutorial creation with LearnPack. Install globally, initiate projects, and customize exercises."
---

# Getting Started with LearnPack as a Creator

There are two use cases that you can take advantage of when using LearnPack. 

The first one is as a [creator](#Creators) of interactive tutorials, and the second use case is as a [learner](#Learners), where you will be consuming interactive tutorials created by the creators.
Find LearnPack at npm, click  to download the package: [click here](https://www.npmjs.com/package/@learnpack/learnpack). 

> ✋ Make sure you have node installed before going to the next step!)

### Start your first tutorial

To create your first tutorial, you have to follow these steps:

1. Install LearnPack globally on your computer by running this command (You should have node installed):

```bash
$ npm install @learnpack/learnpack -g
```

3. Then run this command to start configuring your tutorial

```bash
$ learnpack init
```

This command will ask you everything about your tutorial’s configuration, answer all the questions and your tutorial’s project will be successfully created. These are the questions it will ask you:

First, it will ask you the grading type ([Grading Tutorials](https://4geeks.com/docs/learnpack/grading-learnpack-tutorials)) you want for your tutorial:

A) **Incremental**: In this type of exercise you can’t go to the next exercise until you pass the test of the current one. It is incremental, so further exercises require the knowledge of previous exercises.  

B) **Isolated**: Each exercise is independent so you can go to any exercise in the order you prefer. The latest exercises don’t need earlier exercises’ knowledge.  

C) **No Grading**: These exercises aren’t graded, therefore they don’t have tests.  


![learnpack grading](https://raw.githubusercontent.com/learnpack/docs/main/assets/spaces_db2MUqxH83ZwH273KWpu_uploads_fAt71PHHbRLI1eiXNurN_Untitled%20(1).webp)
​​
4. Next, it will ask for the tutorial’s title.

![learnpack tutorial title](https://github.com/learnpack/docs/blob/main/assets/tutorial-title.png?raw=true)
​​
5. It should ask for the description after the title.

![Description](https://github.com/learnpack/docs/blob/main/assets/description-init.png)
​​

6. Then it will ask you for the difficulty of your tutorial exercises (Beginner, Easy, Intermediate, Hard).
​​![Difficulty](https://github.com/learnpack/docs/blob/main/assets/difficulty.png)


7. The next question will be how many hours it should take to complete the tutorial.
You can just leave this as the default number (1) if you are still not clear of how long the tutorial will be.
​​
It will create all the files of your tutorial and a new directory containing them.  
This is what your project should look like:



![Directory files](https://github.com/learnpack/docs/blob/main/assets/initial-files.png)

​​
Now you have to add the folder of each of the exercises that you are going to add to your tutorial with a structure similar to the one created by the command `$ learnpack init`. 

It should have the `README.md` file, the `test` file, and the entry file (usually called `app.<ext>` where the extension (`ext`) depends on the learning language. For example, if we are building a Python tutorial, it will be `app.py` (this name can be overridden on the configuration options.

The last two files depend on the language you are using.

[Here](#nowhere-still) is a detailed explanation of each file
