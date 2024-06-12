
--- 
description: "Improve your LearnPack configuration with telemetry to unlock key insights and optimize your course management." 
---

# Improve your experience in LearnPack with telemetry configuration

Discover the power of LearnPack and take your course management to the next level by configuring telemetry. This feature is not just about collecting data; it's about unlocking insights that can revolutionize the learning journey. But how do you configure the path for telemetry.json or transmit events as they occur?

### Simplify with learn.json

Each LearnPack course comes with a `learn.json` file, your command center for exercise testing, compiler selection, and more. The "telemetry" key is the latest innovation here, designed to streamline your data tracking.

Check out this example of telemetry key configuration:
![Telemetry Key Example](https://github.com/breatheco-de/content/assets/107764250/70caf7ad-89df-4ead-9404-d7778cd6dd15)

For registered users, LearnPack is always aware, transmitting events for key interactions:
- Pressing the "next" button (event: open_step)
- Running code with the "run" button (event: compile)
- Launching tests with the "run tests" button (event: test)
- Consulting the AI tutor (event: ai_interaction)

### How often is telemetry sent?

Telemetry accumulates events to send them in key situations:

#### Batch
- After executing `learnpack start`: When starting the LearnPack exercise, if telemetry is configured, it will be sent for the first time.
- Opening a new step: After moving from one step to the next, the next step is marked as started and the current copy of telemetry is sent to the configured **batch** URL.

#### Stream
- For each new event, if the stream URL is configured, LearnPack will send information through a webhook to the specified endpoint.

> Remember: For telemetry to work and be sent correctly, you must configure both URLs as specified above.

## What is the structure of telemetry?

Telemetry stores information about each exercise that is opened and when it was done, the results for each compilation or test, each work session, when the tutorial was first started, where it is being worked on, and identifiers for telemetry and the student if it is a 4Geeks student.

Here is an example of what telemetry looks like:
```json
{
    "telemetry_id": "atlbmot8wvalltng",
    "slug": "prompt-engineering-for-beginners",
    "agent": "vscode",
    "tutorial_started_at": 1718211567826,
    "steps": [
        {
            "slug": "00-welcome",
            "position": 0,
            "files": [
                {
                    "path": "exercises\\00-welcome/README.es.md",
                    "name": "README.es.md",
                    "hidden": true
                },
                {
                    "path": "exercises\\00-welcome/README.md",
                    "name": "README.md",
                    "hidden": true
                },
                {
                    "path": "exercises\\00-welcome/__pycache__",
                    "name": "__pycache__",
                    "hidden": true
                }
            ],
            "ai_interactions": [],
            "compilations": [],
            "tests": [],
            "is_testeable": false
        },
        {
            "slug": "01.1-obtain-api-key",
            "position": 3,
            "files": [
                {
                    "path": "exercises\\01.1-obtain-api-key/app.py",
                    "name": "app.py",
                    "hidden": false
                },
                {
                    "path": "exercises\\01.1-obtain-api-key/README.es.md",
                    "name": "README.es.md",
                    "hidden": true
                },
                {
                    "path": "exercises\\01.1-obtain-api-key/README.md",
                    "name": "README.md",
                    "hidden": true
                },
                {
                    "path": "exercises\\01.1-obtain-api-key/test.py",
                    "name": "test.py",
                    "hidden": true
                },
                {
                    "path": "exercises\\01.1-obtain-api-key/__pycache__",
                    "name": "__pycache__",
                    "hidden": true
                }
            ],
            "ai_interactions": [],
            "compilations": [
                {
                    "stderr": "DQpbbm90aWNlXSBBIG5ldyByZWxlYXNlIG9mIHBpcCBhdmFpbGFibGU6IDIyLjMuMSAtPiAyNC4wDQpbbm90aWNlXSBUbyB1cGRhdGUsIHJ1bjogcHl0aG9uLmV4ZSAtbSBwaXAgaW5zdGFsbCAtLXVwZ3JhZGUgcGlwDQo=",
                    "stdout": "RW50ZXIgeW91ciBBUEkga2V5OiBSZXF1aXJlbWVudCBhbHJlYWR5IHNhdGlzZmllZDogcHl0aG9uLWRvdGVudiBpbiBjOlx1c2Vyc1xsZWdpb25cYXBwZGF0YVxsb2NhbFxwcm9ncmFtc1xweXRob25ccHl0aG9uMzExXGxpYlxzaXRlLXBhY2thZ2VzIChmcm9tIC1yIHJlcXVpcmVtZW50cy50eHQgKGxpbmUgMSkpICgxLjAuMSkNClJlcXVpcmVtZW50IGFscmVhZHkgc2F0aXNmaWVkOiBncm9xIGluIGM6XHVzZXJzXGxlZ2lvblxhcHBkYXRhXGxvY2FsXHByb2dyYW1zXHB5dGhvblxweXRob24zMTFcbGliXHNpdGUtcGFja2FnZXMgKGZyb20gLXIgcmVxdWlyZW1lbnRzLnR4dCAobGluZSAyKSkgKDAuOC4wKQ0KUmVxdWlyZW1lbnQgYWxyZWFkeSBzYXRpc2ZpZWQ6IGFueWlvPDUsPj0zLjUuMCBpbiBjOlx1c2Vyc1xsZWdpb25cYXBwZGF0YVxsb2NhbFxwcm9ncmFtc1xweXRob25ccHl0aG9uMzExXGxpYlxzaXRlLXBhY2thZ2VzIChmcm9tIGdyb3EtPi1yIHJlcXVpcmVtZW50cy50eHQgKGxpbmUgMikpICg0LjQuMCkNClJlcXVpcmVtZW50IGFscmVhZHkgc2F0aXNmaWVkOiBkaXN0cm88Miw+PTEuNy4wIGluIGM6XHVzZXJzXGxlZ2lvblxhcHBkYXRhXGxvY2FsXHByb2dyYW1zXHB5dGhvblxweXRob24zMTFcbGliXHNpdGUtcGFja2FnZXMgKGZyb20gZ3JvcS0+LXIgcmVxdWlyZW1lbnRzLnR4dCAobGluZSAyKSkgKDEuOS4wKQ0KUmVxdWlyZW1lbnQgYWxyZWFkeSBzYXRpc2ZpZWQ6IGh0dHB4PDEsPj0wLjIzLjAgaW4gYzpcdXNlcnNcbGVnaW9uXGFwcGRhdGFcbG9jYWxccHJvZ3JhbXNccHl0aG9uXHB5dGhvbjMxMVxsaWJcc2l0ZS1wYWNrYWdlcyAoZnJvbSBncm9xLT4tciByZXF1aXJlbWVudHMudHh0IChsaW5lIDIpKSAoMC4yNy4wKQ0KUmVxdWlyZW1lbnQgYWxyZWFkeSBzYXRpc2ZpZWQ6IHB5ZGFudGljPDMsPj0xLjkuMCBpbiBjOlx1c2Vyc1xsZWdpb25cYXBwZGF0YVxsb2NhbFxwcm9ncmFtc1xweXRob25ccHl0aG9uMzExXGxpYlxzaXRlLXBhY2thZ2VzIA==",
                    "signal": "SIGTERM",
                    "memoryUsage": 532480,
                    "cpuUsage": 0,
                    "errorType": "run-time",
                    "starting_at": 1718211884140,
                    "source_code": "aW1wb3J0IG9zDQojIERPIE5PVCBDSEFOR0UgVEhJUyBDT0RFDQoNCg0KQVBJX0tFWSA9IGlucHV0KCJFbnRlciB5b3VyIEFQSSBrZXk6ICIpDQoNCiMgU2F2ZSB0aGUgQVBJX0tFWSBpbiB0aGUgZG90ZW52IGZpbGUNCndpdGggb3BlbigiLmVudiIsICJ3IikgYXMgZjoNCiAgICBmLndyaXRlKGYiR1JPUV9BUElfS0VZPXtBUElfS0VZfVxuIikNCg0KIyBFeHBvcnQgdGhlIEFQSV9LRVkgYXMgYW4gZW52aXJvbm1lbnQgdmFyaWFibGUNCm9zLmVudmlyb25bIkdST1FfQVBJX0tFWSJdID0gQVBJX0tFWQ0KDQojIEluc3RhbGwgdGhlIGRlcGVuZGVuY2llcyBpbiB0aGUgcmVxdWlyZW1lbnRzLnR4dCBmaWxlDQpwcmludCgiSW5zdGFsbGluZyBkZXBlbmRlbmNpZXMuLi4iKQ0Kb3Muc3lzdGVtKCJwaXAgaW5zdGFsbCAtciByZXF1aXJlbWVudHMudHh0IikNCg==",
                    "ended_at": 1718211886645,
                    "exit_code": null
                }
            ],
            "tests": [
                {
                    "starting_at": 1718211893013,
                    "source_code": "aW1wb3J0IG9zDQojIERPIE5PVCBDSEFOR0UgVEhJUyBDT0RFDQoNCg0KQVBJX0tFWSA9IGlucHV0KCJFbnRlciB5b3VyIEFQSSBrZXk6ICIpDQoNCiMgU2F2ZSB0aGUgQVBJX0tFWSBpbiB0aGUgZG90ZW52IGZpbGUNCndpdGggb3BlbigiLmVudiIsICJ3IikgYXMgZjoNCiAgICBmLndyaXRlKGYiR1JPUV9BUElfS0VZPXtBUElfS0VZfVxuIikNCg0KIyBFeHBvcnQgdGhlIEFQSV9LRVkgYXMgYW4gZW52aXJvbm1lbnQgdmFyaWFibGUNCm9zLmVudmlyb25bIkdST1FfQVBJX0tFWSJdID0gQVBJX0tFWQ0KDQojIEluc3RhbGwgdGhlIGRlcGVuZGVuY2llcyBpbiB0aGUgcmVxdWlyZW1lbnRzLnR4dCBmaWxlDQpwcmludCgiSW5zdGFsbGluZyBkZXBlbmRlbmNpZXMuLi4iKQ0Kb3Muc3lzdGVtKCJwaXAgaW5zdGFsbCAtciByZXF1aXJlbWVudHMudHh0IikNCg==",
                    "ended_at": 1718211893606,
                    "stdout": "G1sxbT09PT09PT09PT09PT09PT09PT09PT09PT09PT09IHRlc3Qgc2Vzc2lvbiBzdGFydHMgPT09PT09PT09PT09PT09PT09PT09PT09PT09PT0bWzBtDQpwbGF0Zm9ybSB3aW4zMiAtLSBQeXRob24gMy4xMS4zLCBweXRlc3QtOC4yLjIsIHBsdWdneS0xLjUuMA0Kcm9vdGRpcjogQzpcVXNlcnNcTEVHSU9OXFByb2plY3RzXGpvYnNcNGdlZWtzXHR1dG9yaWFsc1xwcm9tcHQtZW5nDQpwbHVnaW5zOiBhbnlpby00LjQuMCwgdGVzdGRveC0zLjEuMA0KY29sbGVjdGVkIDEgaXRlbQ0KDQpleGVyY2lzZXNcMDEuMS1vYnRhaW4tYXBpLWtleVx0ZXN0LnB5IBtbMzJtLhtbMG0bWzMybSAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICBbMTAwJV0bWzBtDQoNChtbMzJtPT09PT09PT09PT09PT09PT09PT09PT09PT09PT09IBtbMzJtG1sxbTEgcGFzc2VkG1swbRtbMzJtIGluIDAuMDNzG1swbRtbMzJtID09PT09PT09PT09PT09PT09PT09PT09PT09PT09PRtbMG0NCg==",
                    "stderr": "",
                    "exit_code": 0
                }
            ],
            "is_testeable": true,
            "opened_at": 1718211866688,
            "completed_at": 1718211893606
        },
        {
            "slug": "02-write-your-first-prompt-",
            "position": 4,
            "files": [
                {
                    "path": "exercises\\02-write-your-first-prompt-/prompt.txt",
                    "name": "prompt.txt",
                    "hidden": false
                },
                {
                    "path": "exercises\\02-write-your-first-prompt-/README.es.md",
                    "name": "README.es.md",
                    "hidden": true
                },
                {
                    "path": "exercises\\02-write-your-first-prompt-/README.md",
                    "name": "README.md",
                    "hidden": true
                },
                {
                    "path": "exercises\\02-write-your-first-prompt-/test.py",
                    "name": "test.py",
                    "hidden": true
                },
                {
                    "path": "exercises\\02-write-your-first-prompt-/__pycache__",
                    "name": "__pycache__",
                    "hidden": true
                }
            ],
            "ai_interactions": [],
            "compilations": [],
            "tests": [
                {
                    "starting_at": 1718211911284,
                    "ended_at": 1718211913734,
                    "stdout": "G1sxbT09PT09PT09PT09PT09PT09PT09PT09PT09PT09IHRlc3Qgc2Vzc2lvbiBzdGFydHMgPT09PT09PT09PT09PT09PT09PT09PT09PT09PT0bWzBtDQpwbGF0Zm9ybSB3aW4zMiAtLSBQeXRob24gMy4xMS4zLCBweXRlc3QtOC4yLjIsIHBsdWdneS0xLjUuMA0Kcm9vdGRpcjogQzpcVXNlcnNcTEVHSU9OXFByb2plY3RzXGpvYnNcNGdlZWtzXHR1dG9yaWFsc1xwcm9tcHQtZW5nDQpwbHVnaW5zOiBhbnlpby00LjQuMCwgdGVzdGRveC0zLjEuMA0KY29sbGVjdGVkIDMgaXRlbXMNCg0KZXhlcmNpc2VzXDAyLXdyaXRlLXlvdXItZmlyc3QtcHJvbXB0LVx0ZXN0LnB5IBtbMzJtLhtbMG0bWzMybS4bWzBtG1szMW1GG1swbRtbMzFtICAgICAgICAgICAgICAgICAgICAgICAgWzEwMCVdG1swbQ0KDQo9PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09IEZBSUxVUkVTID09PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09DQobWzMxbRtbMW1fX19fX19fX19fX19fX19fX19fX19fX19fX19fX19fX18gdGVzdF9wcm9tcHQgX19fX19fX19fX19fX19fX19fX19fX19fX19fX19fX19fG1swbQ0KDQogICAgQHB5dGVzdC5tYXJrLml0KCJUaGUgcHJvbXB0IE1VU1QgaW5jbHVkZSBpbmZvcm1hdGlvbiBhYm91dCB0aGUgY2hhcmFjdGVycywgdGhlIHNjZW5lLCBhbmQgYXQgbGVhc3Qgb25lIG1vcmUgZWxlbWVudC4iKQ0KICAgIGRlZiB0ZXN0X3Byb21wdCgpOg0KICAgICAgICBQUk9NUFQgPSBvcGVuKHBhdGgsICJyIikucmVhZCgpDQogICAgICAgIHJlc3VsdCA9IGNyZWF0ZV9wcm9tcHQoVEVTVEVSX1BST01QVCwgUFJPTVBUKQ0KICAgIA0KICAgICAgICBpZiAiQkFEX1BST01QVCIgaW4gcmVzdWx0Og0KICAgICAgICAgICAgc2F2ZV9yZXBvcnQocmVzdWx0KQ0KICAgICAgICBlbHNlOg0KICAgICAgICAgICAgZGVsZXRlX3JlcG9ydCgpDQogICAgDQo+ICAgICAgIGFzc2VydCAiR09PRF9QUk9NUFQiIGluIHJlc3VsdA0KXHgxYlsxbVx4MWJbMzFtRSAgICAgICBhc3NlcnQgJ0dPT0RfUFJPTVBUJyBpbiAiIyBCQURfUFJPTVBUIFxVMDAwMWY2YTlcXG5cXG5JdCBzZWVtcyBsaWtlIHlvdXIgcHJvbXB0IGlzIG1pc3Npbmcgc29tZSBlc3NlbnRpYWwgaW5mb3JtYXRpb24uIFRvIGNyZWF0ZSBhbiBlbmdhZ2luZyBzdG9yeSwgd2UgbmUuLi5lIHRoZXNlIGVzc2VudGlhbCBlbGVtZW50cywgYW5kIEknbGwgYmUgaGFwcHkgdG8gaGVscCB5b3UgY3JlYXRlIGEgY29tcGVsbGluZyBzdG9yeSBhYm91dCBDb29rZW5zaW8sIHRoZSBlbnRyZXByZW5ldXIhIlx4MWJbMG0NCg0KG1sxbRtbMzFtZXhlcmNpc2VzXDAyLXdyaXRlLXlvdXItZmlyc3QtcHJvbXB0LVx0ZXN0LnB5G1swbTo4MzogQXNzZXJ0aW9uRXJyb3INChtbMzZtG1sxbT09PT09PT09PT09PT09PT09PT09PT09PT09PSBzaG9ydCB0ZXN0IHN1bW1hcnkgaW5mbyA9PT09PT09PT09PT09PT09PT09PT09PT09PT0bWzBtDQpceDFiWzMxbUZBSUxFRFx4MWJbMG0gZXhlcmNpc2VzLzAyLXdyaXRlLXlvdXItZmlyc3QtcHJvbXB0LS90ZXN0LnB5OjpceDFiWzFtdGVzdF9wcm9tcHRceDFiWzBtIC0gYXNzZXJ0ICdHT09EX1BST01QVCcgaW4gIiMgQkFEX1BST01QVCBcVTAwMDFmNmE5XFxuXFxuSXQgc2VlbXMgbGlrZSB5b3VyIHByb21wdCBpcyBtaS4uLg0KG1szMW09PT09PT09PT09PT09PT09PT09PT09PT09IBtbMzFtG1sxbTEgZmFpbGVkG1swbSwgG1szMm0yIHBhc3NlZBtbMG0bWzMxbSBpbiAxLjg0cxtbMG0bWzMxbSA9PT09PT09PT09PT09PT09PT09PT09PT09G1swbQ0K",
                    "stderr": "G1sxbT09PT09PT09PT09PT09PT09PT09PT09PT09PT09IHRlc3Qgc2Vzc2lvbiBzdGFydHMgPT09PT09PT09PT09PT09PT09PT09PT09PT09PT0bWzBtDQpwbGF0Zm9ybSB3aW4zMiAtLSBQeXRob24gMy4xMS4zLCBweXRlc3QtOC4yLjIsIHBsdWdneS0xLjUuMA0Kcm9vdGRpcjogQzpcVXNlcnNcTEVHSU9OXFByb2plY3RzXGpvYnNcNGdlZWtzXHR1dG9yaWFsc1xwcm9tcHQtZW5nDQpwbHVnaW5zOiBhbnlpby00LjQuMCwgdGVzdGRveC0zLjEuMA0KY29sbGVjdGVkIDMgaXRlbXMNCg0KZXhlcmNpc2VzXDAyLXdyaXRlLXlvdXItZmlyc3QtcHJvbXB0LVx0ZXN0LnB5IBtbMzJtLhtbMG0bWzMybS4bWzBtG1szMW1GG1swbRtbMzFtICAgICAgICAgICAgICAgICAgICAgICAgWzEwMCVdG1swbQ0KDQo9PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09IEZBSUxVUkVTID09PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09PT09DQobWzMxbRtbMW1fX19fX19fX19fX19fX19fX19fX19fX19fX19fX19fX18gdGVzdF9wcm9tcHQgX19fX19fX19fX19fX19fX19fX19fX19fX19fX19fX19fG1swbQ0KDQogICAgQHB5dGVzdC5tYXJrLml0KCJUaGUgcHJvbXB0IE1VU1QgaW5jbHVkZSBpbmZvcm1hdGlvbiBhYm91dCB0aGUgY2hhcmFjdGVycywgdGhlIHNjZW5lLCBhbmQgYXQgbGVhc3Qgb25lIG1vcmUgZWxlbWVudC4iKQ0KICAgIGRlZiB0ZXN0X3Byb21wdCgpOg0KICAgICAgICBQUk9NUFQgPSBvcGVuKHBhdGgsICJyIikucmVhZCgpDQogICAgICAgIHJlc3VsdCA9IGNyZWF0ZV9wcm9tcHQoVEVTVEVSX1BST01QVCwgUFJPTVBUKQ0KICAgIA0KICAgICAgICBpZiAiQkFEX1BST01QVCIgaW4gcmVzdWx0Og0KICAgICAgICAgICAgc2F2ZV9yZXBvcnQocmVzdWx0KQ0KICAgICAgICBlbHNlOg0KICAgICAgICAgICAgZGVsZXRlX3JlcG9ydCgpDQogICAgDQo+ICAgICAgIGFzc2VydCAiR09PRF9QUk9NUFQiIGluIHJlc3VsdA0KXHgxYlsxbVx4MWJbMzFtRSAgICAgICBhc3NlcnQgJ0dPT0RfUFJPTVBUJyBpbiAiIyBCQURfUFJPTVBUIFxVMDAwMWY2YTlcXG5cXG5JdCBzZWVtcyBsaWtlIHlvdXIgcHJvbXB0IGlzIG1pc3Npbmcgc29tZSBlc3NlbnRpYWwgaW5mb3JtYXRpb24uIFRvIGNyZWF0ZSBhbiBlbmdhZ2luZyBzdG9yeSwgd2UgbmUuLi5lIHRoZXNlIGVzc2VudGlhbCBlbGVtZW50cywgYW5kIEknbGwgYmUgaGFwcHkgdG8gaGVscCB5b3UgY3JlYXRlIGEgY29tcGVsbGluZyBzdG9yeSBhYm91dCBDb29rZW5zaW8sIHRoZSBlbnRyZXByZW5ldXIhIlx4MWJbMG0NCg0KG1sxbRtbMzFtZXhlcmNpc2VzXDAyLXdyaXRlLXlvdXItZmlyc3QtcHJvbXB0LVx0ZXN0LnB5G1swbTo4MzogQXNzZXJ0aW9uRXJyb3INChtbMzZtG1sxbT09PT09PT09PT09PT09PT09PT09PT09PT09PSBzaG9ydCB0ZXN0IHN1bW1hcnkgaW5mbyA9PT09PT09PT09PT09PT09PT09PT09PT09PT0bWzBtDQpceDFiWzMxbUZBSUxFRFx4MWJbMG0gZXhlcmNpc2VzLzAyLXdyaXRlLXlvdXItZmlyc3QtcHJvbXB0LS90ZXN0LnB5OjpceDFiWzFtdGVzdF9wcm9tcHRceDFiWzBtIC0gYXNzZXJ0ICdHT09EX1BST01QVCcgaW4gIiMgQkFEX1BST01QVCBcVTAwMDFmNmE5XFxuXFxuSXQgc2VlbXMgbGlrZSB5b3VyIHByb21wdCBpcyBtaS4uLg0KG1szMW09PT09PT09PT09PT09PT09PT09PT09PT09IBtbMzFtG1sxbTEgZmFpbGVkG1swbSwgG1szMm0yIHBhc3NlZBtbMG0bWzMxbSBpbiAxLjg0cxtbMG0bWzMxbSA9PT09PT09PT09PT09PT09PT09PT09PT09G1swbQ0KLAoKICAgCiAgICAgICAgICAbWzMxbVlvdXIgY29kZSBtdXN0IHRvIGNvbXBseSB3aXRoIHRoZSBmb2xsb3dpbmcgdGVzdHM6G1szOW0gCgogICAgIBtbMzFtG1sxbXggKGZhaWwpG1syMm0bWzM5bSAwLiAbWzM3bVRoZSBwcm9tcHQgTVVTVCBpbmNsdWRlIGluZm9ybWF0aW9uIGFib3V0IHRoZSBjaGFyYWN0ZXJzLCB0aGUgc2NlbmUsIGFuZCBhdCBsZWFzdCBvbmUgbW9yZSBlbGVtZW50LhtbMzltIAoK",
                    "exit_code": 1
                }
            ],
            "is_testeable": true,
            "opened_at": 1718211875020
        },
    ...rest of the files...
    ],
    "workout_session": [
        {
            "started_at": 1718211567826,
            "ended_at": 1718211913735
        },
        {
            "started_at": 1718211952333
        }
    ],
    "last_interaction_at": 1718211913735
}
```


Ensure that your streaming and batch URLs are configured to receive POST requests. It is up to you to devise the logic that will distill the essential data from these interactions.

Dive into the world of telemetry configuration and elevate the educational experience with LearnPack!
