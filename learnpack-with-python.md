# LearnPack With Python

If you want to create a Python coding tutorial, you have to use the [`@learnpack/python`](https://www.npmjs.com/package/@learnpack/python) plugin in order to compile and test your exercises. Go to [Compiler Plugins](/configure#compiler-plugins) to see how to install the plugin.

In addition, the main file should be named `app.py`, and the file for the tests, should be named `test.py`.

### Unit Testing

For testing, you should install [pytest](https://docs.pytest.org/en/7.1.x/contents.html) with the version "4.6.0", pytest-testdox and mock. You can install them by running the following command: `pip3 install pytest==4.6.0 pytest-testdox mock`

If you are not so familiar with `Pytest`, here are the most common tests that you will use when testing a Python exercise tutorial:

### Testing if a variable exists

```py
# test.py

@pytest.mark.it('You should create a variable named variables\_are\_cool')

def test_variable_exists(app):
  
  try:
  
    app.variables\_are\_cool
  
  except AttributeError:
  
    raise AttributeError('The variable "variables\_are\_cool" should exist on app.py')
```

### Testing a variable has the expected value

```py
# test.py

@pytest.mark.it('You should create a variable named myVariable with the value "Hello"')
def test_variable_exists(app):
  try:
    assert app.myVariable \== "Hello"
  except AttributeError:
    raise AttributeError('The variable "myVariable" should exists')
```

### Testing a function exists

```py
# test.py

@pytest.mark.it('You should create a function named "myFunction"')
def test_variable_exists(app):
  try:
    assert app.myFunction
  except AttributeError:
    raise AttributeError('The function "myFunction" should exists')
```

### Testing a function returns the expected value

```py
# test.py

@pytest.mark.it('The function "myFunction" should return the value "Hello World!"')
def test\_variable\_exists(app):
  try:
    assert app.myFunction \== "Hello World!"
  except AttributeError:
    raise AttributeError('The function "myFunction" should exists')
```

### Testing the file with regular expressions:[](#testing-the-file-with-regular-expressions)

```py
# test.py

import os, re

@pytest.mark.it("Create a variable named 'color' with the string value red")

def test_declare_variable():

  path = os.path.dirname(os.path.abspath(__file__))+'/app.py'
  
  with open(path, 'r') as content_file:
  
    content = content_file.read()
    
    regex = re.compile(r"color(\s*)=(\s*)\"red\"")
    
    assert bool(regex.search(content)) == True
```

### Testing a particular string has been printed in the console

```py
# test.py

import io, sys

@pytest.mark.it('The printed value on the console should be "red"')
def test\_for\_file\_output(capsys, app):
  app()
  captured \= capsys.readouterr()
  assert "red\\n" \== captured.out

## Examples

The following links are Python coding tutorials:

*   ​[https://github.com/4GeeksAcademy/python-beginner-programming-exercises](https://github.com/4GeeksAcademy/python-beginner-programming-exercises)​
*   ​[https://github.com/4GeeksAcademy/python-lists-loops-programming-exercises](https://github.com/4GeeksAcademy/python-lists-loops-programming-exercises)​
*   ​[https://github.com/4GeeksAcademy/python-functions-programming-exercises](https://github.com/4GeeksAcademy/python-functions-programming-exercises)​
    
