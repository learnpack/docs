# Empieza a aprender con LearnPack

La forma más fácil de empezar a aprender con LearnPack es iniciar cualquier tutorial a través de Codespaces o Gitpod. [Aquí](https://github.com/4GeeksAcademy/Interactive-Tutorials) tienes una guía con distintos tutoriales que puedes hacer ahora.

## Cómo abrir cualquier tutorial de LearnPack en Codespace o Gitpod

1. Seleccionar el tutorial que te interesa, en este caso, solo clickearé el de [Looping with Javascript](https://github.com/4GeeksAcademy/javascript-arrays-exercises-tutorial) 
![Select tutorial](https://github.com/learnpack/docs/assets/107764250/f9cd5929-972f-462e-b6b9-c7336763c23f)

2. Presionar **Code** y luego **Create codespace on master**
![Create Codespace](https://github.com/learnpack/docs/assets/107764250/982084dd-0053-4ab0-b6b8-d3b2c2037fc5)

3. Cuando el Codespace termine de cargar, ¡está listo!
Ahora solo debes empezar a leer las instrucciones y realizar los ejercicios.
![image](https://github.com/learnpack/docs/assets/107764250/d58a3831-b18a-4799-88be-75e9ed293254)

**Nota**: El proceso para hacerlo con Gitpod es similar. Tan solo debes tener la extensión de Gitpod instalada y te aparecerá un botón que dice **open**.
![Open with Gitpod](https://github.com/learnpack/docs/assets/107764250/366b2185-db53-4781-b304-b0b00cf635e3)


## Cómo usar LearnPack en local

Para usar LearnPack en local tendrás que tener instalado Node > 18.

Puedes instalar la última versión desde [acá](https://nodejs.org/en/download)

1. Instala **LearnPack** con npm:
```node
npm i -g @learnpack/learnpack
```

2. Clona un repositorio de LearnPack
![Clone url](https://github.com/learnpack/docs/assets/107764250/663ee978-fc66-4f8d-9788-3b9f1934ac5a)
Abre la terminal y corre el comando git clone. Ejemplo con el tutorial de Javascript:
```git
git clone https://github.com/4GeeksAcademy/javascript-arrays-exercises-tutorial.git
```

3. Entra al nuevo directorio
Se creará un directorio con el nombre del tutorial, entra en él con el comando cd:
```cmd
cd javascript-arrays-exercises-tutorial
```

4. Ejecuta LearnPack
Cuando instalaste LearnPack globalmente, se agregó una nueva opción a los comandos de tu computadora, ahora puedes ejecutar:
```learnpack
learnpack start
```
En el directorio de un tutorial de LearnPack, y listo.

**Nota**: En caso de que LearnPack detecte que se necesitan plugins que no están instalados para el tutorial que estás haciendo, LearnPack los instalará por ti. Luego solo vuelve a iniciar con **learnpack start**
![Needed plugins](https://github.com/learnpack/docs/assets/107764250/952ba5f4-5a7f-424e-8dfc-856f17f7a4b5)

### Usar LearnPack en local con VSCode

También si tienes VSCode en tu computadora, [instala la extensión de Learnpack](https://marketplace.visualstudio.com/items?itemName=learn-pack.learnpack-vscode). Una vez que estés dentro de un tutorial de LearnPack en VSCode, si es la primera vez que inicias, la extensión de LearnPack ejecutará **learnpack start** por ti.

[//]: # (Corrected mispellings and returned the document in markdown format as requested.)
