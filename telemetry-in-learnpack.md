---
description: "LearnPack Telemetry enhances user experience by tracking interactions and performance metrics, stored locally for improvement analysis."
---


# How **LearnPack Telemetry** works?

Telemetry is a crucial aspect of modern applications, allowing developers to understand how users interact with their software. LearnPack has recently introduced telemetry to enhance user experience by tracking various metrics.

### What does LearnPack know about you?

LearnPack collects information about your usage and stores it in a local file called **telemetry.json** inside the `.learn` hidden directory. This file includes data on compilations, tests, AI interactions (only if you log in), session start/end times, step completion, and when you open a new step. 

Here's a breakdown of the measurements related to your actions:

- **Run Button**: Clicking "run" logs the compilation result, including your code, the standard output (stdout), any errors (stderr), and the exit code.
- **Run Tests Button**: This button initiates the storage of test compilation results, capturing stdout, exit code, source file, execution time, and stderr for errors.
- **New Step**: The first time you hit "next" on an exercise, LearnPack records the time to gauge how long it takes to complete each step.
- **AI Interaction**: For logged-in 4Geeks students, interactions with the AI Tutor are tracked to refine the LLM and develop an optimal tutoring experience.

This data is stored locally, but LearnPack can stream or batch it to any server you specify for analysis. Rest assured, no sensitive personal information is collected—only application usage data to inform improvements.

> 🕵️ Your privacy is important. We only collect non-sensitive usage data to enhance LearnPack's performance and user experience.


For more information about the telemetry, how can be configured for your own needs, please refer to the section [Telemetry Configuration](https://4geeks.com/docs/learnpack/telemetry-configuration)



