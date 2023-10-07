# Keeping Quality on LearnPack Tutorials

## Audit your Tutorial

With LearnPack you can audit your repository checking for possible errors on it.  

You have to run the command learnpack audit to audit your tutorial. This command will check for the following information:

1. The configuration object has `slug`, `repository` and `description`. (Error)
2. The repository shouldn't have user or session information. (Error)
3. Empty or missing `README`, markdown, or tests files. (Error)
4. Scanning the text for `404` or missing links. (Error)
5. Valid image url (Relative or absolute). (Error)
6. The exercise directory names are valid. (Error)
7. The exercises array (Of the config file) doesn’t have content. (Error)
8. Inconsistent translations. (Warning)
9. The .gitignore file doesn’t exist. (Warning)
10. If there is a file within the exercises folder but not inside of any particular exercise folder. (Warning)
