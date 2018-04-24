# Comandos GIT :3

## 1. Alias 

1. git config --global  -l    ---> ver una list de todas las config globales
2. git config --global  alias."nombreAsignado"  "codigo a reemplazar x el asignado"
3. Ej: git config --global alias.s "status -s -b" --> git s  ( mostrará el status en modo silent y la branch)
4. git config --global user.name  "nombre :3"
5. git config --global user.email  "nickname@domain.sex"

6. $ git config --global alias.superlog
"log --graph --abbrev-commit --decorate --date=relative --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all"


## 2. Comandos extras

1. git diff --->  muestra el cambio realizado entre las sentencias ( stage area y local area)
1. git diff staged ---> muestra el cambio  que se encuentra en el stage area
2.  git checkout -- . ------> regresa los cambios al ultimo commit 
3. git reset HEAD "nombre del archivo" --->  sacar un archivo de Stage area
4. git add -- . ( Agrega todo al Stage)
5. git add -u
5. git mv nombreArchivo.txt  nombreNuevo.txt ( renombra el archivo y cambios quedan en el stage area)
6. git rm nombreArchivo.txt ( borra el archivocambios quedan en el stage area)
7. pwd (Muestra la ruta actual)
8. git checkout -- nombre.md ( Regresa ese archivo a su ultimo commit  )

## 3. Comandos Commit 

1. git commit -am "Save directo" --> va del local al repo directo" 
2. git commit --amend -m "Actualizamos el README" --> renombrar el ultimo commit
** git commit --amend ---> cuando no se especifica el msj (hacer los pasos de 3.4 )

3. git reset --soft HEAD^  ---> Regresa a un estado antes del ultimo commit para modificar algo y reemplazar ese commit
4. Cuando se ejecuta lo sgte : git commit ( " sin mensaje ") muesta otra pantalla donde se hará :
* Apretar "A" para escribir el nombre del commit
* Se presionara "ESC"  y luego  ":"  "W" (write) y "Q" (quit)

## 4. Git Reset 

1. git reset --mixed  (HEAD^ o el N° del commit)  ---> regresa el commit pero mantiene los cambios en los archivos del local

2. git reset --hard  (HEAD^ o el N° del commit)  ---> regresa al commit y borra todo delante d ese commit 

3. git reflog ( Muestra todo el historial resets amends ,etc para poder revertir un mal reset )

## 5. Git Ignore 

1. Creamos el archivo .ignore
2. Indicamos que archivos no debe darle seguiento example:  *.log / node_modules / etc

## 6. Ramas ( para fusionar tenemos que estar en la rama que va absover :3)

1. git branch rama-nueva ( creamos la rama)
2. git branch  ( muestra las ramas )
3. git checkout nombreDRama ( nos movemos a la nueva rama)
4. git diff  nombreDeRama master ( Muestras lo cambios entre las ramas)
5. git merge nombreDeRama  ( master absorve cambios de nombreDeRama , si Dios quieres FAST FORWARD)
6. git branch -d rama-villanos ( Despues de terminar la rama se estila b BORRARLA)
7. git checkout -b nombreRama (Crea la rama y hace el cambio a esta.)
8. Para los manual Merge :
		- Resolver los archivos en conflicto  , se mostrará <<<< HEAD CONTENT ======  Conflicht CONTENT =======> Despues realizar el commit

## 6. Git Tag

1. git tag nombreDeTag (release de tu versionado)
2. git tag -d nombreDeTag  ( Borra el tag )
3. git tag -a v1.0.0 -m "Version Stable 1.0.0" ( Crea el nuevo tag y ya sale en el log en que commit fue creado)
4. git tag -a  v0.1.0 345d7de -m "Version Alfa" ( Agregar un tag -  apuntando el commit )
5. git tag ( Muestra los tag creados )
6. git show v1.0.0 ( Muestra detalle del tag)

## 7.  Git Stash

1. WIP  --> Working in Progress
2. git stash ( crea un stash que es como guardar el trabajo dejandolo en stand by (Ya que los archivos se encuentren en el local o el stage ) , hasta resolver otros requerimientos)
3. git stash list ( muestra los stash )
4. git stash pop recupera el ultimo stash (el ultimo inglre y lo elimina) (pero si hay conflicto ver  punto 6.)
5. verficar que se elimino el stash con git log
6. Despues de hacer un la actualizacion de lo cambios manual con el stash y la rama, ahora tenemosgit que borrar el stash con :
git stash drop ( borrará el stash ya no figura en el log)

## 8.  Git Rebase

1. Se ultiliza para traer los cambios realizados en una rama a la rama en al que estamos trabajando , clavando los commits antes 

2. git rebase master ( rama X, trae los cambios hechos en la rama master )

![Image of Yaktocat](http://i.imgur.com/aowdZq7.gif)

3. Uniendo commits ( squash)
	- git rebase -i HEAD~4 ( muestra pantalla con los ultimos 4 commits siendo el ultimo en la lista  el last commit )
	- reescribimos pick por squash (ESC : wq)
	- y luego escribimos el commit name ( :wq )

4. Renombrando el commit 
	- git rebase -i head~1
	-	reemplazar pick por r ( :wq)
	- luego escribir el nuevo nombre del commit

5. Separar commits 
	- git rebase -i head~2
	- reemplazar pick por "edit" (Esc:wq)
	- muestra un mensaje --ammend / --continue
	- git reset HEAD^ ( mandas los archivos al local , y manda al HEAD a ninguna rama)
	- ahora agregar los archivos  al stage y luego el commit , ( acá se separan los commits )
	- git rebase --continue  ( ahora HEAD APUNTARA a Master)

## 9. GitHub / Git  / tags 

1. git push  -u origin master ("ingresamos user y pass origin del nombre d la url remota y master del nombre d la rama")
2. git pull ( para bajar la data del repo remoto y con fastfoward)
3. git fetch ( descarga pero para hacer manual merge)
2. git push --tags ( sube los tags que tengo en el local)
3. git clone  url "nombre d la carpeta" (descarga todo el contenido d un proyecto )

