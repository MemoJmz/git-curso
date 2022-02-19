# git-curso
My first proyect on Git. I started to learn about Git and GitHub. All of the things that I could learn now and later will be here.

Control de versiones a través de Git significa dejar de tener
tarea01.docs
tarea011.docs
tarea011yacasi.docs
tarea01labuena.docs

por tarea01.docs

Git es un sistema de control de versiones, que utilizas con comandos en la consola, mediante repositorios. GitHub es una plataforma de colaboración y control de versiones. Básicamente es Git pero los repositorios no se encuentran en tu equipo. 

Git Documentation
https://git-scm.com/doc

Comandos básicos
---------------------------------------------------------------------------------------------------
Clonar Repositorio
> git clone <https://link-con-nombre-del-repositorio>
Funciona para descargar el código fuente existente desde un repositorio remoto (p.e. GitHub)


Git branch
Usando ramas, varios desarrolladores pueden trabajar en paralelo en el mismo proyecto simultáneamente. Podemos usar el comando para crearlas, listarlas y eliminarlas.

Creando: > git branch <nombre-de-la-rama>
Éste comando creará una rama en local. Para evitar (push) la nueva rama al repositorio remoto, necsitaás usar el isguiente comando
 > git push <nombre-remoto> <nombre-rama>
  
Visualizando ramas:
  > git branch
  > git branch --list
Borrar una rama:
  > git branch -d <nombre-de-la-rama>
  
  
Git Checkout
Para trabajar en una rama, primero tienes que cambiarte a ella. También lo podemos usar para crear archivos y commits.
  > git checkout <nomre-de-la-rama>

Hay algunos pasos que debes seguir para cambiarte exitosamente entre ramas:
Los cambios en tu rama actual tienen que ser confirmados o almacenados en el guardado rápido (stash) antes de que cambies de rama.
La rama a la que te quieras cambiar debe existir en local.
  
Hay también un comando de acceso directo que te permite crear y cambiarte a esa rama al mismo tiempo
  > git checkout -b <nombre-de-tu-rama>
Este comando crea una nueva rama en local (-b viene de rama (branch)) y te cambia a la rama que acabas de crear.
  

Git Status
 Da toda la información necesaria sobre la rama actual
 > git status

 Podemos encontrar información como
  - Si la rama actual está actualizada
  - Si hay algo para confirmar, enviar o recibir (pull).
  - Si hay archivos en preparación(staged), sin prepraración (unstaged) o que no están recibiendo
  - Si hay archivos creados, modificados o eliminados.


Gid Add
  Cuando creamos, modificamos o eliminamos un archivo, estos cambios suceden en local y no se incluirán en el siguiente commit (a menos que cambiemos la configuración).
Necesitamos usar el comando git add para incluir los cambios del o de los archivos en tu siguiente commit.

  - Añadir un único archivo
  > git add <archivo>
  
  - Añadir todo de una vez
  > git add -A

Importante: El comando git add no cambia el repositorio y los cambios que no han sido guardados hasta que no utilicemos el comando de confirmación git commit.
  

Git Commit
  Funciona para guardar nuestros cambios. Git commit  es como establecer un punto de ocntrol en el prodeso de desarrollo al cual puedes volver más tarde si es necesario.
  También necesitamos escribir un mensaje corto para explicar qué hemos desarrollado o modificado en el código fuente.
  > git commit -m "mensaje de confirmación"
  
Importante: Git commit guarda tus cambios únicamente en local
  

Git push
  Después de haber confirmado tus cambios, el sigueinte paso que quieres es enviar tus cambios al servidor remoto. Git push envía tus commits al repositorio remoto.
  > git push <nombre-remoto> <nombre-de-tu-rama>

De todas formas, si tu rama ha sido creada recientemente, puede que tengas que cargar y subir tu rama con el siguiente comando
  > git push -u origin <nombre-de-tu-rama>
  
Importante: Git push solamente carga los cambios que han sido confirmados.
  

Git Pull
  Se utiliza para recibir actualizaciones del repositorio remoto.
  Es una combinación de git fetch (recogemos actualizaciones del repositorio remoto) y de git merge (aplicamos estos últimos cambios en local)
  > git pull <nombre-remoto>

  
Git Revert
  A veces necesitaremos deshacer los camcios que hechos hecho. Hay varias maneras para deshacer nuestro cambios en local y/o en remoto (dependiendo de lo que necesitemos), pero necesitaremos utilizar cuidadosamente estos comandos para evitar borrados no deseados.
  Para ver nuestro historial de commits
  > git log--oneline
  
  Entonces solo necesitamos espedicificar el código de comprobación que encontrarás junto al commit que queremos deshacer
  > git revert #código#
  
  Aparecera una ventana, presiona Shift+q
  El comando git revert deshará el commit que le hemos indicado, pero creará un nuevo commit deshaciendo la anterior.
  
  La ventaja de utilizar git revert es que no afecta al historial de commits. Esto significa que puedes seguir viendo todos los commits en tu historial, incluso los revertidos.

Otra medida de seguridad es que todo sucede en local a no ser que los enviemos al repositorio remoto. Por esto es que git revert es más seguro de usar y es la manera preferida para deshacer los commits.
  
  
  
  
