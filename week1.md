# SkylabCoders Academy
## Full Stack Web Development Bootcamp @Otoño2017

### ~ 20170918

1. MARKDOWN
- Formatear como código:
```javascript
varT1="Esto es una prueba de formato. 🤓"
console.log(T1)
```

2. SYSTEM
- Buscar palabra contenida en ficheros, devuelve fichero y la linea de texto:
```bash
$ grep -R <palabra> <ruta-donde-buscar>
```
- Buscar palabra en ficheros, pero devuelve sólo nombre de ficheros.
```bash
$ grep -Rl <palabra> <ruta-donde-buscar>
```

3. GIT
- Inicializar un repositorio maestro vacio (desnudo):
```bash
app/dirM$ git init --bare
```
- Clonar directorio:
```bash
app/dir1$ git clone ../dir1
```
- Eliminar fichero del staging (antes de commit):
```bash
app/dir1$ git rm --cached <file>
```
o bien:
```
app/dir1$ git reset
```
- Volver al estado "current", último commit del proyecto.
```bash
app/dir1$ git checkout master
```
- Ver histórico de acciones:
```bash
app/dir1$ git log
```
- Recuperar version anterior de fichero:
```bash
app/dir1$ git checkout <commit-id-del-log>
app/dir1$ git checkout -- <file>
```
- Ver diferencias entre estado anterio y actual:
```bash
app/dir2$ git diff HEAD^ HEAD
```
- Ver diferencias a nivel local:
```bash
app/dir2$ git diff HEAD
```
- Añadir servidor remoto:
```bash
app/dir1$ git remote add origin <url-servidor-remoto>
```
- Subir los cambios al servidor remoto:
```bash
app/dir1$ git push -u origin master
```

### ~ 20170919
- Crear una rama del proyecto:
```bash
$ git checkout -b <nombre-de-rama>
```
- Actualizar la rama master con la rama anterior:
```bash
$ git checkout master
$ git merge <nombre-de-rama>
```
- Borrar la rama:
```bash
$ git branch -d <nombre-de-rama>
```

4. JAVASCRIPT
- Tipo de datos: [[enlace]](https://github.com/juanmaguitar/javascript-notes/blob/master/markdown-en/02-variables-data-types-operators/README.md)
    - **Primitives**: number, string, boolean, undefined, null.
    - **Objects**: el resto, para ver tipo de objecto constructor:
        ```javascript
        > Object.prototype.toString.call(new Date())
        "[object Date]"
        ```
        Para ver si es de un tipo en concreto:
        ```javascript
        > x instanceof ObjectoX
        true
        ```
- Prototyping: [[enlace]](https://github.com/juanmaguitar/javascript-notes/blob/master/markdown-en/09-prototype/README.md)
    ```javascript
    > function Animal(name){
        this.name = name;
    }
    > Animal.prototype.type = 'animal';
    > Animal.prototype.eat = function() { console.log('go to eat'); }
    > Animal.prototype.sleep = function() { console.log('go to sleep'); }
    > Animal.prototype
    {type: "animal", eat: f, sleep: f, constructor: f}
    ```
- Heredando prototipo:
    ```javascript
    > function Human(name){
        this.name = name;
    }
    > Human.prototype = new Animal();
    > Human.prototype.speak = function() { console.log('I\'m speaking'); }
    > me = new Human('Ricardo');
    > me instanceof Human
    true
    > me instanceof Animal
    true
    ```
