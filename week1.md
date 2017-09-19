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

