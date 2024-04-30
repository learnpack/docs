# Grading LearnPack Tutorials

Auto-graded exercises are one of the key features offered by LearnPack, it allows the learners to have instant feedback on what they’re learning. You can create the tests using Jest (For html, css, react, javascript, dom) and pytest (Python).  

With LearnPack you can create tutorials with different grading modes, these are the grading modes you can use:  

1. **Incremental**: In this grading mode of exercises, you can’t go to the next exercise until you pass the test of the current one. It is incremental, so further exercises require the knowledge of previous exercises. This grading mode is good for tutorials.
![incremental-example](https://github.com/learnpack/docs/assets/incremental-example.png)

3. **Isolated**: In the isolated mode each exercise is independent so you can go to any exercise in the order you prefer. The latest exercises don’t need earlier exercises’ knowledge.  
4. **No Grading**: These exercises aren’t graded, therefore they don’t have tests.  

## Validate your Unit Tests

The `learnpack test` command allows you to audit each of the exercises' tests. 
This can be done if you have a `solution.hide` file on each exercise, that way the test command will check if the exercises' tests will assert against the solutions.
