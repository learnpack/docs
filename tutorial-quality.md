# Keeping Quality on LearnPack Tutorials

## Audit your Tutorial

With LearnPack you can audit your repository checking for possible errors on it.  

You have to run the `audit` command and learnpack will take care of doing a few important validations.

This is the command:

```bash
$ learnpack audit
```

## LearnPack Audit Errors

The following is the current list of validations performed by the audit command:

1. **Basic learn.json**: The configuration JSON object must have a `slug`, `repository` and `description` property. (Error)

2. **The repository shouldn't have user or session information**: When a learnpack starts running it creates a bunch of files relevant to the current user session completing the exercises (telemetry, login information, etc.). The audit command will make sure you have removed them before publishing the exercises. You can fix that error by running the `$ learnpack clean` command. (Error)
  
3. **Empty or missing files**: Every step in learnpack must have a least one `README` file. (Error)
  
4. **Broken links**: Scan the exercise step instructions (readme files) to make sure there are no links returning 404. (Error)

7. **Valid image url (Relative or absolute)**: Scan all the step exercise instructions to make sure all images are showing up properly. (Error)

8. **The exercise directory names**: LearnPack has a very specific ways on how the exercise step folders should be named, starting with a number and followed with a descriptive folder name. (Error)

9. **The exercises array (Of the config file) doesn’t have content**: There is a file contig.json that gets generated once you start running LearnPack for a particular session and it should be emptied before publishing the exercises. (Error)

## LearnPack Audit Warnings

10. Inconsistent translations. (Warning)

11. The .gitignore file doesn’t exist. (Warning)

12. If there is a file within the exercises folder but not inside of any particular exercise folder. (Warning)
