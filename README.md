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
