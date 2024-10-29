---
tags: ["learnpack"]
title: "How to publish a LearnPack package in the cloud"
---

LearnPack has evolved. Now you can publish your packages in the cloud, so use can access them from anywhere, in any device. During this guide you'll learn how to publish your own LearnPack packages and start sharing them with your friends, colleagues, students and the whole world.

# Prerequisites

- You must have a 4Geeks account. If you don't have one, you can create it [here](https://4geeks.com/pricing).
- Once you created an account, you need to accept the Rigobot invitation in your dashboard.
  ![Rigobot connected](https://raw.githubusercontent.com/learnpack/docs/373d979448fdb782ea499e8f8c19caae2730759d/assets/rigobot-connected.png)
- You must have a _Publisher_ permission in your 4Geeks dashboard. If you don't have it, you can request it by contacting support.

# Publishing a package

1. Open your LearnPack package in your preferred environment, Gitpod, Codespaces or locally.

2. Check that you have the latest version of LearnPack installed by running `learnpack --version` in your terminal. All versions above the 4.0.17 are supported. If you don't have the latest version, you can update LearnPack by running `npm i -g @learnpack/learnpack`.

3. Check the `learn.json` file to ensure that the `editor.version` has a version equal or higher than _4.3.0_. This will ensure that your package is compatible with the latest LearnPack editor, including the new features and improvements such as **Login with GitHub**, **Session Management** and new **Dark Mode**.
   ![learnpack-editor learn.json](https://raw.githubusercontent.com/learnpack/docs/373d979448fdb782ea499e8f8c19caae2730759d/assets/learnpack-editor.png)
4. Run `learnpack publish` in your terminal.

5. Follow the instructions in the terminal to publish your package.

6. Done! Your package is now published and you can share it with anyone.
