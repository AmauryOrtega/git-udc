# Git

Software de control de versiones diseñado por Linus Torvalds.

### Inicio

![imagenes/clone.png](imagenes/clone.png)

```
git clone <URL>
```
URL puede ser:
 - https://github.com/AmauryOrtega/git-udc.git (HTTPS)
 - git@github.com:AmauryOrtega/git-udc.git (SSH)

Por ahora sera con HTTPS asi
```
git clone https://github.com/AmauryOrtega/git-udc.git
```

### Aportando

![imagenes/basic-workflow.png](imagenes/basic-workflow.png)

El estado del repositorio se puede ver con `git status`.

```
[aroc@arch-aroc:Code/git-udc]$ git status                                      
On branch master
Your branch is up-to-date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   README.md

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    modified:   README2.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

    nuevo_archivo

no changes added to commit (use "git add" and/or "git commit -a")
```

 - **Untracked files**: Los archivos no rastreados por git, en este caso `nuevo_archivo` no esta rastreado, para rastrearlo es necesario hacer `git add nuevo_archivo`. Si te encuentras en el directorio del proyecto (la carpeta que se crea al hacer `git clone`), es posible rastrear todos los archivos con `git add .` (Ojo con el '.').
 - **Changes not staged**: Los cambios no seleccionados para crear nuevo commit se pueden seleccionar con los comandios anteriores `git add README.md` o `git add .` en el directorio del proyecto.
 - **Changes to be committed**: Los cambios seleccionados para crear nuevo commit.

Una vez terminado de modificar los archivos y teniendo en *Changes to be committed* los cambios deseados, se hace `git commit -m "Mensaje"`.

Finalmente se suben los cambios al repositorio con `git push origin <branch>`, en este caso sera:

```
git push origin master
```

### Proximo

git reset [file]
Unstages the file, but preserve its contents

git reset --hard [file]

git diff
Shows file differences not yet staged

git diff --staged
Shows file differences between staging and the last file version

#### HTTPS

git config --global user.name "NOMBRE"
git config --global credential.helper cache
git config --global credential.helper 'cache --timeout=3600'
git config --global user.email "email@example.com"

#### SSH

#### BRANCH

##### delete
git branch -d branch_name
git branch -D branch_name
The -d option is an alias for --delete, which only deletes the branch if it has already been fully merged in its upstream branch. You could also use -D, which is an alias for --delete --force, which deletes the branch "irrespective of its merged status."
git push <remote_name> --delete <branch_name>