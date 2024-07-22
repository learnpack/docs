---
tags: ["learnpack"] 
title: "Solutions and Frequently Asked Questions"
---

LearnPack is a product that has had many hours of work invested in it, so to have a better user experience, here are some of the most frequently asked questions about the interface and common errors.

## Frequently Asked Questions
### How do I open the instructions on the right?
To open the LearnPack interface, you have several options:
- Restart LearnPack
  1. Press `Ctrl` + `C` to stop LearnPack
  2. Run `learnpack start` again

If you have the [LearnPack extension](https://marketplace.visualstudio.com/items?itemName=learn-pack.learnpack-vscode) installed in your code editor, the instructions should open automatically.

- Using the editor's `command palette`:
  1. Press `F1` or `Ctrl` + `Shift` + `P`
  2. Type `LearnPack`
  3. Select the `LearnPack: Open Instructions` option


### I don't see the terminal
To open the terminal, you can generally do any of the following:

1. Use the keyboard shortcut `Ctrl` + `J` in your code editor
2. Use the keyboard shortcut `Ctrl` + ` (backtick) in your editor
3. **Quick Command**: Press `Ctrl` + `Shift` + `P` to open the command palette, then type `Terminal: Create New Terminal` and select the option.


### Connection lost!
The connection lost error occurs when the LearnPack interface cannot communicate with the LearnPack server running on your machine. To resolve it, you should ensure that LearnPack is running in a terminal.

- If it is not running, execute: `learnpack start` and wait a few seconds for the interface to reconnect automatically.
- If LearnPack is already running, simply press the `Reload` button that the connection lost modal shows you.


### 'learnpack' is not recognized as an internal or external command
> This message may be different depending on your operating system.

If LearnPack is not installed on your system, the command `learnpack start` and any `learnpack` command won't work. To solve this issue, just install LearnPack on your system with the following command: `npm i -g @learnpack/learnpack`. This will install the latest version of LearnPack from the npm registry globally on your system.

```text
To execute LearnPack locally, you must have Node (> 14) installed.
```
> 💡 You can check if LearnPack is installed with the following command: 
`npm ls -g @learnpack/learnpack`

