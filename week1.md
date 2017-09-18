# SkylabCoders Academy
## Full Stack Web Development Bootcamp @Autumn2017

### ~ 20170918

1. MARKDOWN
- Formatear como código:
```javascript
varT1="Esto es una prueba de formato. 🤓"
console.log(T1)
```

2. SYSTEM
- Buscar palabra contenida en ficheros, devuelve fichero y la linea de texto:
```
$ grep -R <palabra> <ruta-donde-buscar>
```
- Buscar palabra en ficheros, pero devuelve sólo nombre de ficheros.
```
$ grep -Rl <palabra> <ruta-donde-buscar>
```

3. GIT
- Inicializar un repositorio maestro vacio (desnudo):
```
app/dirM$ git init --bare
```
- Clonar directorio:
```
app/dir1$ git clone ../dir1
```
- Deshacer el añadido de fichero en staging (antes de commit):
```
app/dir1$ git rm --cached <file>
```
- Ver histórico de acciones:
```
app/dir1$ git log
```
- Recuperar version anterior de fichero:
```
app/dir1$ git checkout <commit-id-del-log>
app/dir1$ git checkout -- <file>
```
- Ver diferencias entre estado actual y anterior:
```
app/dir2$ git diff HEAD^ HEAD
```
- Ver diferencias a nivel local:
```
app/dir2$ git diff HEAD
```
- Añadir servidor remoto:
```
app/dir1$ git remote add origin <url-servidor-remoto>
```
- Subir los cambios al servidor remoto:
```
app/dir1$ git push -u origin master
```
