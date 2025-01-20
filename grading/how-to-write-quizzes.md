---
title: How to Successfully Create Quizzes for LearnPack 📝
description: Test the knowledge of your users with quizzes in LearnPack
tags: ["learnpack", "quizzes", "markdown", "html", "css"]
---

# How to Successfully Create Quizzes for LearnPack 📝

Quizzes are an engaging and effective way to test a user’s knowledge and comprehension of a topic. They help users think critically and make lessons more interactive. In LearnPack, quizzes are created using **plain markdown** and are rendered into interactive content using specific formatting rules.

In this guide, we’ll explain how to properly structure and format your quizzes to ensure they work seamlessly in LearnPack.

---

## 🔑 Key Rules for Creating Quizzes

### 1. Structure of a Quiz

- **Each question** must have a title, which serves as the question text itself.
- The question title must be **separated by an empty line** from the answer options.
- **Answer options** must be written as a checklist using Markdown’s checkbox syntax (`- [ ]` for incorrect answers, and `- [x]` for the correct answer).

### 2. One Correct Answer

- Each question must have **only one correct answer** to avoid ambiguity and ensure the quiz functions correctly.

### 3. Proper Indentation for Options

- Options must be indented by **3 to 6 spaces** under the question title. (If you’re using an editor like VSCode, pressing `Tab` to indent usually works.)
- Incorrect indentation will cause the quiz to fail when parsed into HTML.

### 4. Empty Line Between Title and Options

- Always **leave a blank line** between the question title and the start of the answer options. This is critical for LearnPack to correctly identify the quiz structure.

---

## 🛠 Formatting Examples

Here are two examples to show you the correct way to format quizzes for LearnPack:

### Example 1: Numbered Questions

```md
1. What is the capital of France?

   - [ ] Berlin
   - [ ] Madrid
   - [x] Paris

2. Which planet is known as the Red Planet?

   - [ ] Earth
   - [x] Mars
   - [ ] Jupiter
```

### Example 2: Bulleted Questions

```md
- What is 2 + 2?

  - [ ] 3
  - [x] 4
  - [ ] 5

- What is the boiling point of water?

  - [x] 100°C
  - [ ] 50°C
  - [ ] 150°C
```

---

## 🚩 Key Notes to Avoid Mistakes

- **Indentation is crucial**: Always use **3 to 6 spaces** for the options.
- **Leave an empty line**: Make sure there is a blank line between the question title and the options.
- **Keep it simple**: Each group of options must have **only one correct answer**.

---

## 🧩 Including Multiple Quizzes in a Lesson

If your lesson contains multiple quizzes, you can include them all in the same markdown file. Just make sure to separate them with an element like a heading, text block, or additional content.

### Example of Multiple Quizzes in One File:

```md
Welcome to the HTML Basics lesson! In this lesson, we will explore the fundamentals of HTML.

### Quiz 1: HTML Basics

1. What is HTML used for?

   - [x] Creating websites
   - [ ] Writing code
   - [ ] Designing animations

2. What does HTML stand for?

   - [ ] Hyper Trainer Markup Language
   - [x] Hyper Text Markup Language
   - [ ] Home Tool Markup Language

---

### Quiz 2: CSS Basics

1. What is CSS used for?

   - [ ] Developing databases
   - [x] Styling websites
   - [ ] Writing server-side code

2. Which property is used to change text color in CSS?

   - [ ] font-color
   - [x] color
   - [ ] text-color
```

---

## 💡 Pro Tips for Quiz Creation

1. **Use a Markdown Editor**: Editors like **VSCode** or **Obsidian** make it easy to write and format markdown files. Use tools like `Shift + Alt + F` in VSCode to auto-format your file, ensuring proper indentation.
2. **Test Your Quiz**: Before publishing, preview your markdown file to ensure the structure works and that the correct answer is clearly marked.
3. **Engage Your Audience**: Write questions that are clear, concise, and relevant to the lesson. Avoid overly complex wording that might confuse the user.

---

By following these guidelines, you’ll create quizzes that are not only functional but also engaging and effective for learners. Quizzes are a great way to reinforce learning, so take the time to craft meaningful questions. Happy teaching! 🎉
