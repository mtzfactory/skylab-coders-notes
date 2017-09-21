# SkylabCoders Academy
## Full Stack Web Development Bootcamp @Otoño2017

## ~ 20170918

### MARKDOWN
- Formatear como código:
```javascript
varT1="Esto es una prueba de formato. 🤓"
console.log(T1)
```

### SYSTEM
- Buscar palabra contenida en ficheros, devuelve fichero y la linea de texto:
```bash
$ grep -R <palabra> <ruta-donde-buscar>
```
- Buscar palabra en ficheros, pero devuelve sólo nombre de ficheros.
```bash
$ grep -Rl <palabra> <ruta-donde-buscar>
```

### GIT
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

## ~ 20170919
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

### JAVASCRIPT
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
    > function Animal(species, name){
        this.species = species;
        this.name = name;
    }
    > Animal.prototype.type = 'animal';
    > Animal.prototype.eat = function() { console.log(this.species + ', going to eat.'); };
    > Animal.prototype.sleep = function() { console.log(this.species + ', going to sleep.'); };
    > var cat = new Animal('cat');
    > var dog = new Animal('dog');
    > Animal.prototype
    Animal {type: 'animal', eat: func, sleep: func}
    ```
- Heredando prototipo:
    ```javascript
    > function Human(name){
        Animal.call(this, 'human', name);
    }
    > Human.prototype = new Animal();
    > Human.prototype.speak = function() { console.log(this.name + ' is speaking.'); }
    > var me = new Human('Ricardo');
    > me instanceof Human;
    true
    > me instanceof Animal;
    true
    ```
- Accessors: getter / setter
    ```javascript
    > function Bike(name) {
        var _name = name;
        this.setName = function() { _name = name; }
        this.getName = function() { return _name; }
    }
    > var bike = Bike('conor');
    > bike.getName();
    "conor"
    > bike.setName('brompton');
    > bike.getName();
    "brompton"
    > bike._name = 'bmx';   // la propiedad _name no pertenece al objeto, pq es una variable interna, y se crea como propiedad nueva
    > bike.getName();
    "brompton"
    ```

## ~ 20170921

### JAVASCRIPT
- **Polifill**: añadir funcionalidades no soportodas por el navegador a los objetos.
    ```javascript
    String.prototype.toCapitalLetter = function() { ... };
    String.prototype.clone = function() { ... };
    ```
- **Hoisting** ~ elevación: (también aplica a la hora de delaración de métodos.)
    ```javascript
    > function f() { x = 5; console.log(x); }
    > x
    ReferenceError: Can t find variable: x
    > f()
    5
    > x
    5
    ```
    Muestra la variable 'x' pq el método 'f()' la define en el scope global, al no estar definida con 'var x;'
    ```
    > function f() { x = 5; console.log(x); var x;}
    > f()
    5
    > x
    ReferenceError: Can t find variable: x
    ```
    Aunque defino 'var x;' al final del método 'f()', hace elevación y se define dentro del scope del propio método.

- **Closures**: scope de las variables. [[enlace]][closure]
    ```javascript
    > function f() { 
        this.x = 5;
        this.fun = function() {
          console.log(x);
        }
      }
    > var v = new f();
    > v.x
    5
    > v.fun()
    ReferenceError: Can t find variable: x
    > function f() { 
        this.x = 5;
        this.fun = function() {
          console.log(this.x);
        }
      }
    > var v = new f();
    > v.x
    5
    > v.fun()
    5
    ```
[closure]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures
- Otro ejemplo: contador de visitas...
    ```
    > var callMe = function() {
        var numCalls = 0
        return function() {
            return ++numCalls
        }
    }()
    > callMe();
    1
    > callMe();
    2
    > callMe();
    3
    ```

### GIT
- Añadir servidor origen **'upstream'** del repositirio que tengo **'fork'** local:
    ```bash
    $ git remote add upstream <url-project-master>
    ```
- Listar configuración de servidores remotos:
    ```bash
    $ git remote -v
    origin  https://github.com/mtzfactory/skylab-bootcamp-201709.git (fetch)
    origin  https://github.com/mtzfactory/skylab-bootcamp-201709.git (push)
    upstream    https://github.com/manuelbarzi/skylab-bootcamp-201709.git (fetch)
    upstream    https://github.com/manuelbarzi/skylab-bootcamp-201709.git (push)
    ```
- Descargar los cambios del **upstream** original, pero no aplicarlos a mi fork local.
    ```bash
    $ git fetch upstream
    ```
- Comprobar en qué rama estoy en mi _working copy_.
    ```bash
    git checkout master
    Already on 'master'
    Your branch is up-to-date with 'origin/master'.
    ```
- Aplicar los cambios descargados con el 'fetch' en mi _working copy_
    ```bash
    $ git merge upstream/master
    ```
- Actualizar **mi** servidor remoto 'origin', rama 'master':
    ```bash
    $ git push origin master
    ```

