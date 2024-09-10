# Terminal

Es la ventana que almacena la shell, la shell es una linea de comandos que interpreta comandos del usuario y los ejecuta en el sistema operativo.

Algunos shell son:
a. Bourne Shell
b. Bash Shell: son las mas comunes
c. Z Shell: son las mas comunes
d. C Shell
e. Korn Shell
f. Fish Shell
g. PowerShell: es para windows, que usa los comandos de forma diferente.

Bash en r linux.

Un comando es un programa que se puede ejecutar desde la terminal y puede recibir parametros y opciones.

# aprendiendo a caminar en la terminal

En un sistema linux o wsl, con un sistema de archivos o rutas por las cuales caminar, todo inicia en un slash / o raiz de archivos y desciende como si fuera un arbol. Tenemos dev, hom, usr, etc.

Dentro de la carpeta de home hay directorios donde se almacena la informacion de las y los usuarios.

Vere,mos las ventajas de la terminal.

Tendremos el nombre del equipo o el host name

~ hace referencia al directorio

```sh

ls
// lista el sistema de archivo

~
// dice que estamos en la carpeta de home

cd
// change directory dice que necesita recibir un parametro para moverse a cierto directorio

cd pictures
// nos movemos a la carpeta de pictures

clear
// limpia la terminal

ctr + l
// limpia la terminal

ls -l
// -l long de cuando fue creado cuanto pesa, con informacion detallada

ls -lh
// -lh para una lectura detallada

cd
// regresar a home

cd Document
// te lleva a la carpeta Document si es que existe

cd ..
// te regresa una carpeta atras

pwd
// print woring document, te imprime en que documento te encuentras

## existe rutas absolutas y rutas relativas

# ruta absoluta
/root/terminal

cd /root/terminal
// para ir a una ruta especificia

# ruta relativa es
.
// para estar dentro del directorio actual como
cd ./test/index.tsx

cd ..
// nos regresa un directorio
# en este caso a 'terminal'

file README
// describe el tipo de archivo, con tab se puede autocompletar el nombre del archivo

```

# Manipulando archivos y directorios

Hablaremos en esta ocasion sobre los comandos para manipular archivos, pero tambien otras variantes del comando ls

```sh

ls -la
// para ver los directorios, incluso los escondidos
// se muestran con un punto al principio . , linux los masrtca como ocultos

ls -lS
// con S mayuscula es S de size, los ordena por tamanio

ls -lr
// los muestra de reversa

tree
// muestra todos los directorios como si fuera un arbol, muestra todas las carpetas pero puede no ser user friendly

tree -L 2
// es de niveles, le puedes decir en cuantos niveles profundice, en este caso 2
## puede que requieras instalar este comadno y se instala con  snap install tree o apt  install tree

```

Para modificar o crear directorio, se usan los siguientes comandos?

```sh

mkdir miDirectorio
// de preferencia sin espacios, pero si quieres con espacios, seria de la siguientes manera

mkdir 'Mi Directorio'

touch miArchivo
// esto crea archivos

# para crear archivos o directorios, se pueden crear muchos a la vez

mkdir dir1 dir2 dir3
// se crean todos esos directorios

touch file1 file2 file3
// crea los 3 archivos con sus respectivos nombres

cp file1 file_
// este comando en primer lugar pone el archivo que quieres copiar, y en segundo con que nombre, si no especificas donde copiarlo, lo copiara en la misma carpeta

mv file_ ..
// mueve el archivo una carpeta atras

mv file_bk copy
// cambia el nombre del archivo

rm copy
// borra el archivo especifico

rm -i miArchivo
// pone un menu interactivo para confirmar si quieres borrar o no el archivo
# y borra
# no lo mantiente

mv test tost
// mueve la carpeta test dentr tost

rm -r
// puede borrar archivos

rm -ri
// puede borrar archivos con flag para confirmar

rm -rf
// borra todo por default sin preguntarse

```

# Que es un comando?

Un comando puede ser 4 cosas

a. Un programa ejecutable
b. Un comando de utilidad de la shell: vienen internas en el programa
c. Una funcoin de shell: funciones de shell externas, existen formas de programar en el shell
d. Un alias

## Que es un alias?

```sh
type cd
// nos dice el tipo de comando que estamos usando
# cd is a shell builtin

type mkdir
# mkdir is hashed (/usr/bin/mkdir)

type ls
# ls is aliased to `ls --color=auto'
// de hecho no es un comando normal de ls, e inscluso puede recibir parametros

```

Para crear alias haremos lo siguiente

```sh
alias l='ls -lh'
// resuimiria todo ese comando a l
# pero no duran para toda la vida
total 16K
-rw-r--r-- 1 root root 4.4K Sep  9 22:43 README.md
drwxr-xr-x 3 root root 4.0K Sep  9 22:04 tost
drwxr-xr-x 3 root root 4.0K Sep  9 22:07 tust

// solo perduran si son variables de entorno

help cd
// te da la informacion de los comandos

ls --help
// es otra forma de buscar mas informacion de un comando

# help es una utilidad del shell, con otra bash podria no funcionar

man
# manual deusuario de un ocmando

man cd
// te da una explicacion detallada de un comando

info cd
// es muy similar a man

whatis cd
// te da un descricpcion simple de un comando


```
