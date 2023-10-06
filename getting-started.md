# Getting Started with LearnPack (Quick Start)

There are two use cases that you can take advantage of when using LearnPack. 

The first one is as a [creator](#Creators) of interactive tutorials, and the second use case is as a [learner](#Learners), where you will be consuming interactive tutorials created by the creators.
Find LearnPack at npm, click  to download the package: [click here](https://www.npmjs.com/package/@learnpack/learnpack). 

> ✋ Make sure you have node installed before going to the next step!)

## Creators

### Start your first tutorial

In order to create your first tutorial, you have to follow these steps:

1. Install LearnPack globally on your computer by running this command (You should have node installed): `$ npm install @learnpack/learnpack -g`
2. Go to the path where you want to save the tutorial’s repository, and create the directory where you want them to be: `$ mkdir name-of-tutorials`
3. Then run this command to start configuring your tutorial: `$ learnpack init`
This command will ask you everything about your tutorial’s configuration, answer all the questions and your tutorial’s project will be successfully created. These are the questions it will ask you:

First, it will ask you the grading type () you want for your tutorial:
A) **Incremental**: In this type of exercise you can’t go to the next exercise until you pass the test of the current one. It is incremental, so further exercises require the knowledge of previous exercises.
B) **Isolated**: Each exercise is independent so you can go to any exercise in the order you prefer. The latest exercises don’t need earlier exercises’ knowledge.
C) **No Grading**: These exercises aren’t graded, therefore they don’t have tests.
​​
Now it will ask for the tutorial’s title.
​​
It should ask for the description after the title.
​​
Then it will ask you for the difficulty of your tutorial exercises (Beginner, Easy, Intermediate, Hard).
​​
The next question will be how many hours it should take to complete the tutorial.
​​
It will create all the files of your tutorial.
This is what your project should look like:
​​
Now you have to add the folder of each of the exercises that you are going to add to your tutorial with a structure similar to the one created by the command learnpack init . It should have the  file, the test file, and the entry file, the last two files depend on the language you are using.

## Learners
In order to install it, run the npm install @learnpack/learnpack -g.
Install the tutorial you want to use by executing the following command: learnpack download <name-of-tutorial> or you can choose the tutorial by running learnpack download this will display a list of all the tutorials.
Install the LearnPack plugin that you need depending on the programming language that the tutorial uses. here is more information about .
After installing everything, the last step to start using LearnPack, is running the command learnpack start
Ready to start learning!
