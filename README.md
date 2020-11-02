## Git Init
Git Init - Inicializador del Repositorio
Git add . - Agregando los Archivos del Directorio al Staging Area
Git Commit -m ¨Message¨ - Agregando los Archivos del Staging Area al Repositorio nuevo.

## Checkout
- Git CheckOut - Atrae la ultima version del Repo's de la rama ubicada. 

## Staging Area
Git add . - Agregando los Archivos del Directorio al Staging Area

## Rm + Cached
 - Git rm Historia.txt -  Elimina los archivos del área de Staging y del próximo commit pero los mantiene en nuestro disco duro.
 - Git rm --cached Historia txt Básicamente removimos el archivo que quedo en la cache de la memoria ram
 - ¿Cual es la diferencia entre RM cuando esta cacheado y cuando no tiene el cached?
Cach significa que este esta en memoria ram, que no esta todavia guardado en la Base de datos.
- Elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).

## Git Log
- Git Log - Mostrar la informacion de los Commits hechos
- Git Log NombreArchivo - Mostrar la informacion de los Commits hechos a un archivo
- Git Log --OneLine - Mostrar la informacion de los Commits hechos de una forma mas resumida.
- Git Log --stat - Mostrar los cambios hechos en un archivo de una manera mas especifica
- git log --oneline - Te muestra el id commit y el título del commit.
- git log --decorate- Te muestra donde se encuentra el head point en el log.
- git log --stat - Explica el número de líneas que se cambiaron brevemente.
- git log -p- Explica el número de líneas que se cambiaron y te muestra que se cambió en el contenido.
- git shortlog - Indica que commits ha realizado un usuario, mostrando el usuario y el titulo de sus commits.
- git log --graph --oneline --decorate y
- git log --pretty=format:"%cn hizo un commit %h el dia %cd" - Muestra mensajes personalizados de los commits.
- git log -3 - Limitamos el número de commits.
- git log --after=“2018-1-2” ,
- git log --after=“today” y
- git log --after=“2018-1-2” --before=“today” - Commits para localizar por fechas.
- git log --author=“Name Author” - Commits realizados por autor que cumplan exactamente con el nombre.
- git log --grep=“INVIE” - Busca los commits que cumplan tal cual está escrito entre las comillas.
- git log --grep=“INVIE” –i- Busca los commits que cumplan sin importar mayúsculas o minúsculas.
- git log – index.html- Busca los commits en un archivo en específico.
- git log -S “Por contenido”- Buscar los commits con el contenido dentro del archivo.
- git log > log.txt - guardar los logs en un archivo txt


## Configuracion de Github
1. Git Config - Informacion de toda la configuracion de tu archivo config de Git.
2. Git Config --Global - Refiriendome a que haremos una configuracion global.
3. Git Config --Globar user.name "Usuario" - Configuracion del usuario de Git.
4. Git Config --Global user.email "Email" - Configuracion del Email de Git.

## Git Show

- Git Show - Muestra la informacion de los cambios de un archivo.
- Git Diff - Muestra la comparacion de cambios dependiendo del commit.

	`
		git diff V01 V02 V03
    `

## Git Reset
 - Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir. No hay vuelta atrás.

Este comando es muy peligroso y debemos usarlo solo en caso de emergencia.

- git reset --soft: Borramos todo el historial y los registros de Git pero guardamos los cambios que tengamos en Staging, así podemos aplicar las últimas actualizaciones a un nuevo commit.

- git reset --hard: Borra todo. Todo todito, absolutamente todo. Toda la información de los commits y del área de staging se borra del historial.

- git reset HEAD, lo único que haremos será mover estos cambios de Staging a Unstaged. Seguiremos teniendo los últimos cambios del archivo, el repositorio mantendrá el archivo (no con sus últimos cambios pero sí con los últimos en los que hicimos commit) y no habremos perdido nada.

## Git CheckOut

- Git checkout numeroCommit NombreArchivo de ese commit - Regreso a la version de ese archivo al punto del numeroCommit de la rama. 

`
git checkout ef31ace785e0802013a7e3dfe9690249014a9b65 historia.txt
`
Colocando asi el punto en el commit que se ralizo de la rama. Por lo tanto para volver a la rama MASTER solo hay que usar:

- Git checkout master nombreArchivo - Se vuelve a la version master de x Archivo.(Peligroso)

> 	Git Checkout nombreRama

Se mueve a la rama que escribamos.


## Git Branch

- Git branch - Muestra las Ramas creadas y tambien se usa para
crear otra rama.

- Git show-branch: nos muestra las ramas y su historia
- Git show-branch --all: nos muestra e forma mas detallada las ramas

#### OJO
>	Gitk: nos muestra una version grafica de nuestra historia


- Git checkout -b nombrederama: con esto podemos crear y saltar a una rama a la vez

## Git Merge 

- Git merge - Permite unir ramas. 

>     Hacer merge desde la rama que quieres unir

## Git PULL

1. - Elegir URL del repositorio.
2. - Git remote add origin url copiada

>	AGREGAMOS UN ORIGIN PARA HACER FETCH Y PULL

3. - Git push origin master

>	GIT ENVIA LA RAMA MASTER A EL REPOSITORIO

4. - Git pull origin master --ALLOW-UNRELATED-HISTORIES

>	GIT TRAEME LOS DATOS DEL REPO'S HACIA MI RAMA MASTER
>	CREA UN MERGE CON LA RAMA MASTER DESDE REMOTE

## CONFIGURACION SSH

- Lave SSH: (Cualquier sistema operativo)

- ssh-keygen -t rsa -b 4096 -C 

>	"youremail@example.com"

Comprobar proceso y agregarlo (Windows)

eval $(ssh-agent - s)
ssh-add ~/.ssh/id_rsa
Comprobar proceso y agregarlo (Mac)

>     eval "$(ssh-agent -s)"

- ¿Usas macOS Sierra 10.12.2 o superior? Haz lo siguiente:

>	cd ~/.ssh

Crea un archivo config…
Con Vim vim config
Con VSCode code config
Pega la siguiente configuración en el archivo…

## Git tag's

* Git tag - Muestra los tags creados
* Git tag -a -m "Mensaje" HASH

>	git tag -a V0.1 -m "1.1 Inicio del Proyecto" 72b3210

>`-a AGREGAR | -m MENSAJE | HASH NUMERO DE COMMIT`

* Git tag -d nameTag - Eliminar tag.

* git push origin :refs/tags/nametag
>	REFERENCIA PARA ACTUALIZAR TAGS

## Stashed:
- El stashed nos sirve para guardar cambios para después, Es una lista de estados que nos guarda algunos cambios que hicimos en Staging para poder cambiar de rama sin perder el trabajo que todavía no guardamos en un commit

- Ésto es especialmente útil porque hay veces que no se permite cambiar de rama, ésto porque porque tenemos cambios sin guardar, no siempre es un cambio lo suficientemente bueno como para hacer un commit, pero no queremos perder ese código en el que estuvimos trabajando.

- El stashed nos permite cambiar de ramas, hacer cambios, trabajar en otras cosas y, más adelante, retomar el trabajo con los archivos que teníamos en Staging pero que podemos recuperar ya que los guardamos en el Stash.

>     git stash

- El comando git stash guarda el trabajo actual del Staging en una lista diseñada para ser temporal llamada Stash, para que pueda ser recuperado en el futuro.

- Para agregar los cambios al stash se utiliza el comando:


> 	git stash save "mensaje identificador del elemento del stashed"

- Obtener elelmentos del stash
El stashed se comporta como una Stack de datos comportándose de manera tipo LIFO (del inglés Last In, First Out, «último en entrar, primero en salir»), así podemos acceder al método pop.

- El método pop recuperará y sacará de la lista el último estado del stashed y lo insertará en el staging area, por lo que es importante saber en qué branch te encuentras para poder recuperarlo, ya que el stash será agnóstico a la rama o estado en el que te encuentres, siempre recuperará los cambios que hiciste en el lugar que lo llamas.

- Para recuperar los últimos cambios desde el stash a tu staging area utiliza el comando:

>	git stash pop
    
- Para aplicar los cambios de un stash específico y eliminarlo del stash:

>     git stash pop stash@{<num_stash>}
 
- Para retomar los cambios de una posición específica del Stash puedes utilizar el comando:

>	git stash apply stash@{<num_stash>}

- Donde el <num_stash> lo obtienes desden el git stash list

- Listado de elementos en el stash
Para ver la lista de cambios guardados en Stash y así poder recuperarlos o hacer algo con ellos podemos utilizar el comando:

>     git stash list

- Retomar los cambios de una posición específica del Stash || Aplica los cambios de un stash específico

- Crear una rama con el stash
Para crear una rama y aplicar el stash mas reciente podemos utilizar el comando

>	git stash branch <nombre_de_la_rama>

- Si deseas crear una rama y aplicar un stash específico (obtenido desde git stash list) puedes utilizar el comando:

>	git stash branch nombre_de_rama stash@{<num_stash>}

- Al utilizar estos comandos crearás una rama con el nombre <nombre_de_la_rama>, te pasarás a ella y tendrás el stash especificado en tu staging area.

- Eliminar elementos del stash
Para eliminar los cambios más recientes dentro del stash (el elemento 0), podemos utilizar el comando:

>	git stash drop

- Pero si en cambio conoces el índice del stash que quieres borrar (mediante git stash list) puedes utilizar el comando:

>	git stash drop stash@{<num_stash>}

-	Donde el <num_stash> es el índice del cambio guardado.

- Si en cambio deseas eliminar todos los elementos del stash, puedes utilizar:

>	git stash clear

-	_ Consideraciones:_

- El cambio más reciente (al crear un stash) SIEMPRE recibe el valor 0 y los que estaban antes aumentan su valor.
Al crear un stash tomará los archivos que han sido modificados y eliminados. Para que tome un archivo creado es necesario agregarlo al Staging Area con git add [nombre_archivo] con la intención de que git tenga un seguimiento de ese archivo, o también utilizando el comando git stash -u (que guardará en el stash los archivos que no estén en el staging).
Al aplicar un stash este no se elimina, es buena práctica eliminarlo.


## Git Clean

- Simula lo que se va a borrar sin borrarlo.


>	git clean --dry-run 

- Borra archivos, no carpetas. Solamente las cosas que puede indexar. Tampoco borrara los archivos que estan .gitignore.


>	Git clean -f


## Git Cherry-Pick


>	MALA PRACTICA



##	Git nunca olvida, git reflog
- Git guarda todos los cambios aunque decidas borrarlos, al borrar un cambio lo que estás haciendo sólo es actualizar la punta del branch, para gestionar éstas puntas existe un mecanismo llamado registros de referencia o reflogs.

- La gestión de estos cambios es mediante los hash’es de referencia (o ref) que son apuntadores a los commits.

- Los recoges registran cuándo se actualizaron las referencias de Git en el repositorio local (sólo en el local), por lo que si deseas ver cómo has modificado la historia puedes utilizar el comando:

>	git reflog


- Muchos comandos de Git aceptan un parámetro para especificar una referencia o “ref”, que es un puntero a una confirmación sobre todo los comandos:

>	 git checkout 
	 
-	Puedes moverte sin realizar ningún cambio al commit exacto de la ref

>	git checkout eff544f


>	git reset
	
- Hará que el último commit sea el pasado por la ref, usar este comando sólo si sabes exactamente qué estás haciendo

>	git reset --hard eff544f 
	
- Perderá todo lo que se encuentra en staging y en el Working directory y se moverá el head al commit eff544f
git reset --soft eff544f # Te recuperará todos los cambios que tengas diferentes al commit eff544f, los agregará al staging area y moverá el head al commit eff544f
git merge: Puedes hacer merge de un commit en específico, funciona igual que con una branch, pero te hace el merge del estado específico del commit mandado

>	git checkout master

>	git merge eff544f 

-	Fusionará en un nuevo commit la historia de master con el momento específico en el que vive eff544f

## Git Grepp

- git grep color -->use la palabra color
- git grep la --> donde use la palabra la
- git grep -n color–> en que lineas use la palabra color
- git grep -n platzi --> en que lineas use la palabra platzi
- git grep -c la --> cuantas veces use la palabra la
- git grep -c paltzi --> cuantas veces use la palabra platzi
- git grep -c “<p>”–> cuantas veces use la etiqueta <p>
- git log-S “cabecera” --> cuantas veces use la palabra cabecera en
todos los commits.

- grep–> para los archivos
- log --> para los commits.

## COMANDOS Y RECURSOS COLABORATIVOS EN GIT Y GITHUB

- git shortlog -sn = muestra cuantos commit han hecho cada miembros del equipo.
- git shortlog -sn --all = muestra cuantos commit han hecho cada miembros del equipo hasta los que han sido eliminado
- git shortlog -sn --all --no-merge = muestra cuantos commit han hecho cada miembros quitando los eliminados sin los merges
- git blame ARCHIVO = muestra quien hizo cada cosa linea por linea
- git COMANDO --help = muestra como funciona el comando.
- git blame ARCHIVO -Llinea_inicial,linea_final= muestra quien hizo cada cosa linea por linea indicándole desde que linea ver ejemplo -L35,50
- **git branch -r **= se muestran todas las ramas remotas
- git branch -a = se muestran todas las ramas tanto locales como remotas
    
## Observaciones
Se utiliza un solo guión(- Letra) para acceder a un comando de una letra. Ejemplo:
git commit -am ¨Mi commit"
Se utiliza dos guiones(-- Palabra) para acceder a un comando de una palabra. Ejemplo:
git config --global

    
>	Git checkout

 - Si se hace un checkout hacia un punto de la historia en la rama ubicada y hacemos un cambio seguido de un commit. Ese commit se hara dentro de ese punto de la historia. Reemplazando ese commit en el punto de la historia donde nos ubicamos.


> 	Git commit -am

- Este sirve para agregar al stage y crear un commit al mismo tiempo solo si esos archivos han sido agregados por primera vez al stage.