# Evaluación de Tutoriales en LearnPack
Las ejercicios autoevaluados son una de las características clave ofrecidas por LearnPack, permiten a los aprendices obtener retroalimentación instantánea sobre lo que están aprendiendo. Puedes crear las pruebas utilizando Jest (para HTML, CSS, React, JavaScript, DOM) y pytest (Python).

Con LearnPack, puedes crear tutoriales con diferentes modos de evaluación, estos son los modos de evaluación que puedes utilizar:

1. **Incremental**: En este modo de evaluación de ejercicios, no puedes pasar al siguiente ejercicio hasta que apruebes la prueba del actual. Es incremental, por lo que los ejercicios posteriores requieren el conocimiento de los ejercicios anteriores. Este modo de evaluación es bueno para tutoriales. ![ejemplo-incremental](https://github.com/learnpack/docs/blob/ecc84406fbac09dbb0061c838c565a267a3b92c1/assets/incremental-example.png)
2. **Aislado**: En el modo aislado, cada ejercicio es independiente, por lo que puedes ir a cualquier ejercicio en el orden que prefieras. Los ejercicios más recientes no necesitan el conocimiento de los ejercicios anteriores.
3. **Sin Evaluación**: Estos ejercicios no son evaluados, por lo tanto, no tienen pruebas.

## Validar tus Pruebas Unitarias
El comando `learnpack test` permite auditar las pruebas de cada uno de los ejercicios. Esto se puede hacer si tienes un archivo `solution.hide` en cada ejercicio, de esa manera el comando de prueba verificará si las pruebas de los ejercicios afirmarán contra las soluciones.
