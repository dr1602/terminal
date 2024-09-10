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

https://platzi.com/blog/41-comandos-terminal/

https://platzi.com/cursos/bash-shell/

cowsay -f dragon-and-cow s

```

# Wildcards

Una serie de caracteres especiales que nos permite encontrar patrones o realizar busquedas mucho mas avanzadas, este tipo de busquedas sera con el comando ls, en lugar deusar ls indscriminadameten, mejor usamos wildcards para encontrar cierto patron como .txt, .html o que empiecen con mayuscula.

```sh

mkdir new

touch file.txt dot.txt dot2.txt index.html datos.tsx datos datos123 abc

ls *.txt
// encuentra los archivos que terminan con txt

ls datos*
// muestra todos los archivos que empiecen con datos y terminen con cualquier otra cantidad y variedad de datos

ls datos?
// por favor busca todas las palabras que tengan datos al principios y que solo tenga un caracter al final

ls dato???
// busca el archivo que comience con dato y que tenga 3 caracteres al final

ls *.html
// encuentra los archivos que terminan con html

ls [[:upper:]]*
// muestra solo un caracter con mayuscula y que tenga cualquier terminacion, las wirldcards buscan en al menos dos niveles de contenido de las carpetas.

# las wildcards no son expreisones regulares aunque se parezcan

ls -d [[:upper:]]*
// para solo buscar las carpetas

ls [[:lower:]]*
// muestra todos los archivos que empiecen con minuscula

# hacer clases con wildcards
ls []
// busqeuda por caracteres

ls [ad]*
// busca los archivos que empiecen con a o con d y que tenga cualquier terminacion

```

## otros wildcards

https://static.platzi.com/media/public/uploads/command-line-cheat-sheet_f2552bde-3bb0-4b1c-a1a7-dbd40095fa4f.pdf

## Retos de la clase

Crear alias de utilidad, buscar todos los archivos js dentro de script, y buscar archivos que empiecen con numeros

```sh

ls [:alnum:]*
// Coincide con cualquier caracter alfanumerico

ls [:digit:]*
// coincide con cualquier numero

# para buscar archivos de tsx
alias tsx='ls *tsx'
```

# Redirecciones: como funciona la shell

Ingresamos texto y tenemos un output, aprenderemos a manejar dichas entradas y salidas para tener diferentes utilidades.

Normalmente tenemos una entrada que se le conoce como Standar Input que proviene de nuestro teclado pero tambien lo podemos dirigir desde archivos de texto y se describe como 0 dentro de la terminal. A esos numeros se les conoce como file descriptors.

Tiene dos opciones de salida:
a. Standar output, que muestre todos los directorios. Su file descriptor es 1.
b. stderr: que muestre errores is n encuentra nada. Su file descriptor es 2.

```sh

ls
//para saber que tengo

ls Pictures > mis_archivo.txt
// redereicciona Pircutres a el nuevo archivo mis_archivo.txt, al menos el nombre

# otra variante
ls *.txt > mis_archivo.txt

less mis_archivo.txt
// para ver que hay dentro de mis_archivo.txt
// tenemos el nombre de todos los archivos que finalizan con .txt

ls *.tsx > mis_archivo.txt


less mis_archivo.txt
// para ver que hay dentro de mis_archivo.txt
// siempre sobre escribe, no los concatena

# para concatenar:

ls *.txt >> mis_archivo.txt

less mis_archivo.txt
// para ver que hay dentro de mis_archivo.txt
// ahora si los concatenalos concatena


# que pasa con los errores
ls adsgfasdgasd
// marca error

ls adsgfasdgasd > error.txt
// para mandar al error a un archivo
// aunque muestre error, si crea el archivo pero no tiene nada, solo redirige el std output, para redirigirlo se necesita es pexificar std error

head error.txt
// no muestra nada por lo antes mendcionado

ls adsgfasdgasd 2> error.txt
// mandamos el error

head error.txt
// ahora si tenemos la info guardada del error

# para redirigr tanto el stdoutput y el error es:
ls adsgfasdgasd > output.txt 2>&1
// primero se redirige al error y luego con & tambien con el output

ls Documents > output.txt 2>&1
less output.txt

```

las redirecciones sirven para, por ejemplo, ver errores despues. Como en un servidor que muestra errores pero que no los guarda, pero hay que tener cuidado porque sobre escribe archivos.

Investiga el stdinput, o como redirigido, y buscar un ejemplo de como utilizarlo.

```sh
touch input.txt

code input.txt

# redirigin stninput desde un archivo
cat < input.txt

# es igual a
cat input.txt
```

# Redireccioens: pipe operator

El pipe operator, permite operar un comenado que su stdop, puede funcionar coo stdin puede desencadenar filtros, encadenamientos, funcionalides, que pueden terminar en la generacion de un archivo.

Antes de comenzar

```sh

echo 'hola Platzi'
// genera un stdop de cualquier comando que ejecutemos

less error.txt

less output.txt

cat error.txt output.txt
// sirve para concatenar la salida de los archivos

cat < error.txt
# ls: cannot access 'adsgfasdgasd': No such file or directory

stdin no se usa tan frecuente en la terminal, tal vez la redireccion pero en casos de uso en especifico, pero es importante como los comandos que nos permiten explorar teto como cat, les, head, tail, hacen uso de esta funconaldiad stin para mostrarlo como stdou

```

## pipe operator

nos permite que el stdout se convierta en el stdin de otro comando como con:

```sh
ls -lh | less
// lo redirigimos al comando less e incluso asi podemos buscar cn slash atraves del documento

# asi ya no se necesita crear un archivo

# si se necesita crear un del output despues de verlo con less, seria

ls -lh | less | tee output.txt
// el tee hace los mismo que la redireccion < permitiendonos dejandolo guardar un archivo incluso dejandolo pasar a traves de los pikes

# para ver que hay dentro del archivo
cat cat output.txt
// muestra lo mismo

# el comando lo estamos usando al reves, deberia de ser asi
ls -lh | tee output.txt | less

cat output.txt
// con este comando vemos que nos lo crea


# otro comando con el pipe perator es pasarlo por un filtro cmo un comando sort que lo va a ordernar

ls -lh *.tsx | sort | tee tsx.txt | less

ls -lh | sort | tee output.txt | less
# te sales de la consola de comandos con q

cat output.txt
# es una manera util de buscar

# para instalar a la vaquita y al lol cat
sudo apt install cowsay

sudo apt install lolcat

cowsay 'hola'

echo 'Hola Platzi' | lolcat
// lo genera en colores como si fuera arcoiris

# para tener una vaca colorida

cowsay 'Hola Platzi' | lolcat

# para guardar la vaca en un archiv, que pasaria con lol cat?
# porque al pasar el stoup, seguramente no lo maneja correctamente para dirigirlo a tee

cowsay 'Hola Platzi' | lolcat | tee vaca.txt
// hay que tenerlo en cuenta


```
