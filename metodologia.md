# Metodología de la práctica final 

## Pasos ejecutados para la realización de la práctica

Para realizar la práctica final debíamos compilar todos los trabajos realizados a lo largo del curso en un mismo repositorio. Este nuevo repositorio tenía que estar dentro de la organización de Github Pontedatos, a la que fui añadida por el profesor. En ella tuve que crear el repositorio IreneAcosta a través de la pestaña “New repository” en la que puse mi nombre y en la pestaña “owner” seleccioné “Pontedatos”, esto significa que el profesor es dueño del repositorio y aparece así en su organización.

Una vez creado mi repositorio, abandono Github para realizar todos los siguientes pasos a través de mi terminal. A través de esta tengo que unir mi repositorio de Pontedatos con la misma terminal, es decir copiar el repositorio Git en mi directorio local. Esto lo realicé a través de la función `git.clone` copiando después la URL del código de mi repositorio Git. Comprobé que está acción se había realizado de manera correcta con el comando `ls -a` para ver que se había clonado el Git creando un nuevo directorio local para el repositorio.

No obstante, como bien avisa la propia terminal, este directorio está vacío, por ello a través del comando `cp`  que se utiliza para copiar el contenido del directorio con todas mis prácticas a este fichero nuevo denominado IreneAcosta.  Este comando tiene la siguiente estructura `cp [opciones] [origen] [destino]` en opciones puse el nombre de todos los archivos, el origen la carpeta en la que los tenía y en destino puse la nueva carpeta IreneAcosta. De nuevo, para comprobar que los archivos se habían copiado correctamente utilicé el comando de listar archivos dentro de este directorio, `ls -a`.

Ya con todos las prácticas en IreneAcosta me dispuse a subirlos a mi repositorio en Pontedatos. Aunque previamente había realizado con la nueva url el comando `git clone`, para comprobar que el repositorio remoto es correcto ejecuté el comando `git remote -v` que me mostraba la url donde lo extraigo (`fetch`) y donde lo vuelca o lo sube (`push`). En el siguiente paso se subieron todos los archivos a mi repositorio de Github, para ello se realizan los siguientes pasos: 

1. Ejecutamos el comando `git status` que nos muestra el estado del directorio de trabajo y nos permite ver los cambios realizados, los archivos que se han subido a git o no o ver los cambios reparados y no. 
2. Ejecutamos el comando `git add .` con la que se añaden los archivos  
3. Ejecutamos el comando `git commit .`  con el que se comitean los cambios 
4. Ejecutamos el comando `git push` con el que se carga el contenido de del repositorio local al repositorio remoto, en este caso de Github. 

En mi caso no me dio ningún error estos pasos, no obstante, para ver que los pasos se han realizado correctamente o conocer el estado del git se puede usar el comando `git status`. Del mismo modo, en otras prácticas el comando `git pull` me ha servido cuando el comando `git push` me daba error debido a diferentes cuestiones. Este comando,  `git pull`, permite actualizar los contenidos de los repositorios. 

### Creación de una página web a través de Github 

Como explicó el profesor en clase se utiliza la funcionalidad "Pages" de Github con la que se puede crear web con el contenido de nuestro repositorio. Para activar esta opción de "Pages" a través de la url:  https://github.com/Pontedatos/nombre-repositorio/settings/pages. En esta página seleccionamos la opción “master” (esta es la que me salía a mí, aunque el profesor indica que debe ser “main” investigué y es lo mismo), después selecciono carpeta /root/.  Así Github crea una web cuya  estructura será la de mi repositorio, en el que el archivo README.md Github lo convierte Github en index.html. 

