# How to teach with LearnPack?

LearnPack consists of several connected applications, a CLI that allows you to install plugins, start tutorials, or restart them completely to delete temporary files. In addition to a VSCode extension that allows you to open a React interface so that the student can read the instructions, run their code, talk to Rigobot AI, and perform more actions.

![LearnPack CLI](https://github.com/learnpack/docs/assets/107764250/7cf98dd0-6144-4b06-9543-aecaee3bb470)

LearnPack courses consist of different exercises that are stored within an **exercises** directory. Here you can see an example:

![Example files](https://github.com/learnpack/docs/assets/107764250/eafb68d1-4dda-443c-8b69-6683069a0f1d)

Let me explain what each file is for:

- README.md: These are the instructions for each of the exercises, in this case in English by default. You can add more languages by adding the language extension, for example, for Spanish: README.es.md
- app.js / app.py / index.html: This is the main file that the student will need to edit, you can have default content or start from scratch, depending on how you want to do the course. LearnPack will automatically open this file when the student is on the exercise.
- test(s).js / test(s).py: These are the files for testing the student's code, they are optional, if the tutorial is for: Node, Dom, HTML, or React, you should use test.js, if it is for Python, then you will use test.py. In the case of Javascript, the tests are evaluated using Jest, in the case of Python, with Pytest.
- solution.hide.html / solution.hide.js / solution.hide.css / solution.hide.py: These are files that contain the solution to the exercise problem, it is optional, you can include it to ensure that the student can pass the tutorial without problems.

Additionally, if you add any other file, LearnPack will also open it for the student when they are in the exercise, feel free to add all the necessary files for the exercise.
