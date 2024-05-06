---
description: "Kickstart your coding journey with LearnPack! Easily access tutorials via Codespaces, Gitpod, or locally with detailed guides."
---

# Start Learning with LearnPack

The easiest way to start learning with LearnPack is to initiate any tutorial through Codespaces or Gitpod. [Here](https://github.com/4GeeksAcademy/Interactive-Tutorials) you have a guide with different tutorials you can do now.

## How to open any LearnPack tutorial in Codespace or Gitpod

1. Select the tutorial you are interested in, in this case, I will just click on [Looping with Javascript](https://github.com/4GeeksAcademy/javascript-arrays-exercises-tutorial)
![Select tutorial](https://github.com/learnpack/docs/assets/107764250/f9cd5929-972f-462e-b6b9-c7336763c23f)

2. Press **Code** and then **Create codespace on master**
![Create Codespace](https://github.com/learnpack/docs/assets/107764250/982084dd-0053-4ab0-b6b8-d3b2c2037fc5)

3. When the Codespace finishes loading, it's ready!
Now you just have to start reading the instructions and doing the exercises.
![image](https://github.com/learnpack/docs/assets/107764250/d58a3831-b18a-4799-88be-75e9ed293254)

**Note**: The process with Gitpod is similar. Just have the Gitpod extension installed and you will see a button that says **open**.
![Open with Gitpod](https://github.com/learnpack/docs/assets/107764250/366b2185-db53-4781-b304-b0b00cf635e3)

## How to use LearnPack locally

To use LearnPack locally you will need to have Node > 18 installed.

You can install the latest version from [here](https://nodejs.org/en/download)

1. Install **LearnPack** with npm:
```node
npm i -g @learnpack/learnpack
```

2. Clone a LearnPack repository
![Clone url](https://github.com/learnpack/docs/assets/107764250/663ee978-fc66-4f8d-9788-3b9f1934ac5a)
Open the terminal and run the git clone command. Example with the Javascript tutorial:
```git
git clone https://github.com/4GeeksAcademy/javascript-arrays-exercises-tutorial.git
```

3. Enter the new directory
A directory with the name of the tutorial will be created, enter it with the cd command:
```cmd
cd javascript-arrays-exercises-tutorial
```

4. Execute LearnPack
When you installed LearnPack globally, a new option was added to your computer's commands, now you can execute:
```learnpack
learnpack start
```
In the directory of a LearnPack tutorial, and you're done.

**Note**: In case LearnPack detects that plugins not installed are needed for the tutorial you are doing, LearnPack will install them for you. Then just restart with **learnpack start**
![Needed plugins](https://github.com/learnpack/docs/assets/107764250/952ba5f4-5a7f-424e-8dfc-856f17f7a4b5)

### Use LearnPack locally with VSCode

Also, if you have VSCode on your computer, [install the Learnpack extension](https://marketplace.visualstudio.com/items?itemName=learn-pack.learnpack-vscode). Once you are inside a LearnPack tutorial in VSCode, if it is the first time you start, the LearnPack extension will execute **learnpack start** for you.
