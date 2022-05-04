# Documentación del proceso de aprendizaje en clase 

En este apartado se documenta el proceso de aprendizaje de contenidos en la asignatura de Periodismo de Datos, un proceso que también ha derivado en la realización de esta práctica final donde se compilan todas las prácticas con sus correspondientes explicaciones. El periodismo de datos es algo que está en el día a día de un periodista, nace en 2006-2008 con el predominio del software de código abierto, el Open Data o el HTML. Como vimos en clase actualmente la visualización de datos siempre pasa por un registro electrónico, por un ordenador y por la web. Tomando esto como base, en la asignatura se impartieron contenidos para el uso de un periodismo de datos, conociendo nuestros ordenadores y su funcionamiento. A continuación se muestran algunos de los contenidos aprendidos. 

## Lenguaje Markdown 

Fue de las primeras lecciones de la asignatura. Para adentrarnos en el mundo del periodismo de datos web comenzamos aprendiendo sobre lenguaje markdown que viene a ser dos cosas principalmente: 

- Un lenguaje “de marcado ligero” que nos permite crear contenido de manera sencilla de escribir, y que en todo momento mantenga un diseño legible. 
- Software, un "parseador" o conversor de esa sintaxis en HTML 
Lo destacable del lenguaje Markdown es que no importa si finalmente se necesita un PDF o un HTML sino que siempre podrás publicar los documentos como tú los has diseñado, se pueden obtener estos formatos de archivos a través de conversores. 

## Instalación de un programa de emulación de la terminal

Un emulador de terminal es un programa de software que simula el funcionamiento de una terminal del equipo local,la terminal es un intérprete de comandos. El emulador de terminal hace uso de interfaces gráficas de usuario, puede proporcionar acceso interactivo a las aplicaciones que sólo se ejecutan en entornos de línea de comandos de Shell. En el curso utilizamos dos emuladores de terminales, tanto Ubuntu como Cygwin, en mi caso he utilizado ambos porque ninguno me dio problemas. 

### WSL (Windows Subsystem for Linux)

Comenzamos el curso con [WSL (Windows Subsystem for Linux)](https://docs.microsoft.com/es-es/windows/wsl/about) es una terminal que nos permite ejecutar un entorno de GNU/Linux, virtualizado por M$ para Windows 10. Para poder activar la terminal tuvimos que iniciar [PowerShell](https://docs.microsoft.com/es-es/powershell/scripting/overview?view=powershell-7.2) que, como explican Windows, es  “una solución de automatización de tareas multiplataforma formada por un shell de línea de comandos, un lenguaje de scripting y un marco de administración de configuración”. Iniciando la aplicación como administrador ejecutamos en ella `wsl -install -d Ubuntu` que instala la terminal o  sistema operativo [Ubuntu GNU/Linux](https://ubuntu.com/); que es una una distribución de código abierto basado en Linux. 

### Cygwin

En el curso, debido a que Ubuntu daba algunos problemas,  por ello procedimos a instalar en nuestros ordenadores [Cygwin, que como explica en su página web es](https://www.cygwin.com/): “ un granconjunto de herramientas GNU y de código abierto que brindan una funcionalidad similar a una distribución Linux en Windows. Además, de una una librería DLL (Dynamic Link Library) que proporciona una funcionalidad API POSIX”.  Para instalar Cygwin tuvimos que descargar desde su página, después a través del gestor de paquetes de Cygwin instalamos diferentes paquetes buscándolos: libcurl4, lynx, wget,
ca-certificates-letsencrypt, nano y openssl.

## Configuración del programa

### 1. Creamos un alias

Tras instalar nuestro programa de emulación de la terminal, Ubuntu en mi caso, realizamos unas configuraciones para facilitar el uso de la misma. Entre las primeras acciones realizadas, y una de las más importantes para agilizar los procesos, creamos un alias para crear un acceso directo a una carpeta sin tener que escribir y buscar toda la ruta.
Primero, nombramos este alias como `micasa` para que nos lleve a la ruta deseada en mi caso, `cd/mnt/c/users/ireac/desktop/datos/github`,  debemos escribir el siguiente comando para denominarlo así: `micasa = “cd/mnt/c/users/ireac/desktop/datos/github”`. 

El siguiente paso fue ejecutar el comando `echo '"alias micasa = ‘cd/mnt/c/users/ireac/desktop/datos/github'"`, este comando solo lo que hace es imprimir el mismo texto. A continuación,  configuramos la variable de entorno home,  modificando los archivos de configuración de la shell (que como veremos más adelante en nuestro caso usamos bash). Por ello crearemos un archivo en `.bashrc`, es importante mecionar que a través del comando `>>` en sell significa la salida de un comando o programa que es dirigido a uno nuevo, se escriben dos signos de mayor porque agrega lo nuevo al final. El comando final para poder crear nuestro alias será:  `echo `”alias micasa = ‘cd/mnt/c/users/ireac/desktop/datos/github’ ” >>$HOME/.bashrc`. 
 
Para comprobar que ha funcionado correctamente y si escribimos micasa, nos lleva a la carpeta,  utilizamos el comando `cat` (es una forma con la que mostrar el contenido de un archivo en la línea de comando) por ello si escribimos `cat>>$HOME/.bashrc`  podremos ver el archivo al final.  En mi caso estaba bien hecho, pero si lo hubiera escrito mal se edita y corrige a través del comando: `nano $HOME/.bashrc` . 

Por último, ejecutaremos el comando `source $home/.bashrc`. Este comando es muy importante porque con este  recargamos las modificaciones realizadas en el archivo `.bashrc` y así los mismos cambios se realizarán al momento.  

### 2. Configuración git

Primero debemos comprender que es Git. Microsoft lo define como [“un sistema de control de versiones distribuido. Esto significa que un clon local del proyecto es un repositorio de control de versiones completo”.](https://docs.microsoft.com/es-es/devops/develop/git/what-is-git). En nuestro caso utilizaremos `git` como nuestro software para el sistema de control y a través de `git` conseguiremos  vincular nuestra terminal con un repositorio remoto, en nuestro caso un repositorio de Github.

Para conseguir realizar esta vinculación, tenemos que ir a la carpeta de Periodismo de Datos y en ella clonar el repositorio de nuestro Github para vincularlo con nuestra terminal. Para ello, en el repositorio copiamos el enlace https del código (code) y en la terminal lo clonamos a través del comando: `git clone [url]` . Ahí para comprobar que se nos ha clonado el repositorio remoto a nuestro directorio podemos ejecutar el comando `ls` para ver el listado de archivos dentro del directorio. 

A través del comando `git commit --amend --reset-author` deshacemos con este el commit porque nos impone una autoría previa. El siguiente comando a ralizar es  `git config --global user.name [nombre del usuario de Github]` y después `git config --global user.email [correo del usuario de Github]` con estos pasos vinculamos nuestro usuario de Github.  Para guardar todo esto realizamos `git commit`. Por último, con `git config --global set-editor nano` escogemos que el editor de texto predeterminado sea siempre nano. 

Podemos corroborar a qué repositorio se ha conectado a través del comando `git remote -v` que nos da la url `FETCH` que nos dice donde extraigo los datos y la url `PUSH` donde vuelca o sube los archivos.  

## Configuración de un programa de edición de texto 

Fue necesario configurar un programa de edición de texto para poder, desde nuestra propia terminal, editar o crear un texto sin un formato específico en lenguaje Markdown. En nuestro caso el profesor nos recomendó utilizar el editor de texto nano.

### Ubuntu - WSL 

Para configurar nano en el caso de no tenerlo configurado en la WSL de Ubuntu tendríamos que ejecutar los comandos  `sudo apt-get update` y después `sudo apt-get install nano`. Para configurar nano ejecutamos el comando echo/root/.nanorc. Dentro de la configuración, para evitar que las líneas de texto sean infinitas y para enumerarlas tenemos que ejecutar 

`nano $HOME/.nanorc` y en el texto añadimos:
`# Esto lo hago para ajustar el texto a pantalla` 
`set softwrap`
`# Esto para numerar las líneas`
`set linenumbers`

Tras configurar el programa de edición de texto salimos de este `crtl + x`; damos a guardar y escribimos el nombre del archivo. 

### Cygwin 

En Cygwin ya teníamos instalado nano, para comprobarlo escribimos en la terminal `nano` y este se abre. De nuevo, al igual que hicimos en WSL, configuramos que aparezcan las líneas numeradas a través de `set linenumbers`. 

## Configuración y funcionamiento de un gestor de paquetes/programas del emulador de la terminal

Un gestor de paquetes es “un sistema o conjunto de herramientas que se usa para automatizar la instalación, actualización, configuración y uso de software. La mayoría de los administradores de paquetes están diseñados para detectar e instalar las herramientas de desarrollo”, según explican desde [la página web de Microsoft](https://docs.microsoft.com/es-es/windows/package-manager/). 

En el caso del sistema Ubuntu GNU/Linux el gestor de paquetes es `apt` con el que podemos instalar, actualizar e incluso eliminar paquetes de software dentro de la terminal. Por otro lado, en Cygwin encontramos que la terminal ya tiene su propio gestor de paquetes: `apt-cyg`. 

## Versión del lenguaje de SHELL utilizado.

En el caso de la terminal de Ubuntu `Bash` es el intérprete de lenguaje de comandos, es decir uno de los lenguajes posibles de Shell. Para conocer que Shell utilizamos podemos utilizar el comando `echo $0` que nos devolverá a partir de esta variable de entorno la shell que estamos utilizando en el caso de WSL nos devuelve `-BASH`. 


## Valor de la variable de entorno PATH.

Las variables de entorno en mi caso la variable de entorno es `$PATH` propia de los sistemas de Microsoft. En esta se detallan las rutas, un listado de directorios separada por puto y comas de directores, en los cuales el intérprete de comandos puede ejecutar. Para ver el valor de la variable `PATH` podemos imprimirla directamente a través del comando `echo $PATH`.

Las variables de entorno tienen al principio el signo `$` si por ejemplo ponemos simplemente `$PATH` la terminal nos muestra las rutas con los programas que son posibles ejecutar. Si por ejemplo, quisieramos saber el valor de las rutas de la variable escribiríamos `echo. echo $PATH`. 

## Comandos utilizados y ejemplos.

Aunque ya se han mostrado algunos de los comandos utilizados para la instalación y el uso de la terminal, a lo largo de nuestro aprendizaje hemos aprendido diferentes. Aunque, lo primero que comprendimos fue la estructura básica de las aplicaciones:  $ COMANDO/OPCIONES/ARGUMENTO.  El comando es una instrucción que realiza una función específica como lo es `pwd` que nos dice donde estamos; las opciones especifica como queremos que nos muestre esa información que nos da el comando;  y el argumento es de donde queremos que lo coja. Por ejemplo, con el comando  `ls/-l/ ` nos lista en formato extendido el directorio  y toda su información.  

**Lista de comandos utilizados en clase:** 

- `pwd` = donde estoy 
-  `ls [ruta del directorio]`
- `cd` = cambiar de directorio 
- `mv  [origen] [destino]` = comando para mover no renombrar archivos o directorios, en argumentos tenemos que detallar el origen y destino. 
- `cp [origen] [destino]` = copiar y pegar archivos.
- `man` = es el comando del manual de la terminal. `Q` para salir del manual.
- `mkdir [nombre carpeta]` = comando con el que creamos una carpeta
- `cat` = con este comando visualizamos un archivo desde la misma terminal. 
- `echo` = la terminal con este comando nos lo devuelva un texto. Por ejemplo, si queremos saber cuál es nuestra variable de entorno home debemos poner `echo $HOME`. 
- `env` = visualizamos con este comando todas las variables de entorno. Al ser tantas debemos escribir `env | less` para ver de manera más asequible este enorme listado. 
- `nano` = se abre con el  programa de edición de texto nano que nos permite crear o editar los textos 
- Comandos Git = aunque muchos se han explicado con anterioridad, en este punto detallamos algunos nuevos y recordamos el resto. 
-- `git clone` = comando con el que clonamos un repositorio remoto en nuestro directorio local.
--  `git config` = con este comando definimos los valores de configuración de git.Como hemos visto anteriormente: `git config --global user.name`;  `git config --global user.email`;  `git config --global set-editor nano`.
--  `git status` = comando que nos muestra el estado del directorio de trabajo y del área de entorno. Nos permite ver los cambios que se han realizado, los que se han reparado o no, en los que Git no puede vincular etc. 
--  `git add “nombre-archivo”` o `git add .` = este comando nos permite añadir los cambios del directorio al entorno de ensayo, es decir con este comando le dices a Git las actualizaciones que quieres realizar. A través del argumento `.` añades todos los nuevos archivos, cambios etc. 
--  `git commit -m “lo que comiteamos” ` o `git commit .` = con este comando realizamos el commit es decir el cambio que hemos realizado se verá con esta acción en GitHub. A través del argumento `.` añades todos los nuevos archivos, cambios etc. 
--  `git push` =  se usa este comando para cargar el contenido del repositorio local al repositorio remoto de Github (en nuestro caso) . Este paso es el último que realizaremos para actualizar los cambios que veíamos en `Git Status`.
--   `git pull` =  permite actualizar los contenidos de los repositorios. 
-- `git remote -v`

