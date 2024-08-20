---
tags: ["learnpack"] 
title: "Agent and Mode in LearnPack"
authors: ["Charlytoc"]
---

## What is the Agent in LearnPack
LearnPack is an application with various small parts connected to each other. When you run LearnPack inside Visual Studio Code, it is slightly different from running it in a browser. Due to these implementation differences, it is possible to configure LearnPack to open as a VSCode extension (agent = "vscode") or to open the interface in the browser (agent = "os").

## What is the "mode" in LearnPack
LearnPack will notice in which program it was executed to determine the agent, but the agent can also be specified within `learn.json` in the `editor.agent` section. This allows users to explicitly define how they want LearnPack to be executed.

If a difference is detected between the detected agent and the suggested one, LearnPack will display a warning. This warning is important to ensure the best user experience, as each agent has its own characteristics and advantages.

For example, if LearnPack detects that it is running in VSCode but the `learn.json` file suggests that it should run in a browser, a message will be displayed recommending changing the agent to avoid potential compatibility or functionality issues.

## How to run LearnPack within agent "os"
To run LearnPack as agent "os", follow these steps:

1. **Close VSCode**:
   - Save your work and close the VSCode application.

2. **Open a new terminal**:
   - Open a terminal or command prompt on your operating system.

3. **Navigate to your LearnPack project directory**:
   - Use the `cd` command to navigate to the directory where your LearnPack project is located.

4. **Run LearnPack**:
   - Execute the following command to start LearnPack:
     ```sh
     learnpack start
     ```

## How to run LearnPack from VSCode
To run LearnPack as a VSCode extension, follow these steps:

1. **Open VSCode**:
   - Launch the Visual Studio Code application on your computer.

2. **Install the LearnPack extension**:
   - Go to the Extensions view by clicking the Extensions icon in the Activity Bar on the side of the window or by pressing `Ctrl+Shift+X`.
   - Search for "LearnPack" and click "Install".
   - If the extension is already installed but disabled, enable it.

3. **Open your terminal in VSCode**:
   - Open your terminal in VSCode.

4. **Navigate to your LearnPack project directory**:
   - Use the `cd` command to navigate to the directory where your LearnPack project is located.

5. **Run LearnPack**:
   - Execute the following command to start LearnPack:
     ```sh
     learnpack start
     ```
