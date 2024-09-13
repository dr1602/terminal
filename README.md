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

# Operadores de control

Son simbolos reservados que permiten encadenar comandos, ya sea de manera sincrona o asincrona
como

```sh

ls; mkdir holi; cal

encadena los comandos que son leer, crear y mostrar calendario

// antes de ejecutar cal, se necesita instalar con:
apt install ncal

// se ejecutan de manera sincrona
ls; mkdir holi; cal

README.md  error.txt  holi  input.txt  new  output.txt  tost  tsx.txt  tust  vaca.txt
mkdir: cannot create directory ‘holi’: File exists
   September 2024
Su Mo Tu We Th Fr Sa
 1  2  3  4  5  6  7
 8  9 10 11 12 13 14
15 16 17 18 19 20 21
22 23 24 25 26 27 28
29 30

# ahora lo vamos a ejecutar de manera asincrona con un hilo de procesador con cada linea de comandos que se ejecuten pero hay que tener cuidado para que los comandos no se ejecuten indefindamente, se hacen cada comando con una consola aparte en segundo plano

ls & date & cal

[1] 30518
[2] 30519
   September 2024
Su Mo Tu We Th Fr Sa
 1  2  3  4  5  6  7
 8  9 10 11 12 13 14
15 16 17 18 19 20 21
22 23 24 25 26 27 28
29 30

README.md  error.txt  holi  input.txt  new  output.txt  tost  tsx.txt  tust  vaca.txt
Fri Sep 13 10:18:47 CST 2024
[1]-  Done                    ls --color=auto
[2]+  Done                    date

```

ahora veremos como correr comandos de forma condicional

```sh
# para hacerlo de forma condicional se usa &&

mkdir test && cd test

root@DESKTOP-JGJI4A4:~/terminal# mkdir test && cd test
root@DESKTOP-JGJI4A4:~/terminal/test#


# que pasaria si hago esto con forma incorrecta?

mir test && cd tost && echo 'carpeta creada'

cd tesdadst && cd tost && echo 'carpeta creada'

//cd tesdadst && cd tost && echo 'carpeta creada'
//bash: cd: tesdadst: No such file or directory

# para poder ejecutar comandos aunque sea de forma incorrecta tipo asincrono pero no es asincrono porque no crea nuevos hilos

cd tesdadst || touch archiv.tsx || ls || echo 'carpeta creada'

// cd tesdadst || touch archiv.tsx || ls || echo 'carpeta creada'
// bash: cd: tesdadst: No such file or directory
// root@DESKTOP-JGJI4A4:~/terminal/test# ls
// archiv.tsx

cd asdsdfasdf || echo 'Cambio de directorio'

// cd asdsdfasdf || echo 'Cambio de directorio'
// bash: cd: asdsdfasdf: No such file or directory
// Cambio de directorio

```

para desarrollo web te puedes enfrentar a webpack para ver desarrollo de manera activa, webpack ve si se ejecuta un archivo, si se ejeceuta de forma correcta, ejecuta otros mas.

## reto

hacer la ejecucion donde si se vea que el archivo se creo exitosamente.

```sh
cd tesdadst || touch segundo_test.tsx; ls && echo 'carpeta creada'

// cd tesdadst || touch segundo_test.tsx; ls && echo 'carpeta creada'
// bash: cd: tesdadst: No such file or directory
// archiv.tsx  segundo_test.tsx
// carpeta creada
```

# Como se manejan los permisos:

## Tipos de archivos

Tipos de archivo, que incluso se ven con ls para ver el tipo de permiso, son:

- archivo normal
  d un directorio
  l un link simbolico
  b archivo de bloque especial, son archivos que manejan informacion la informacion de los bloque sde datos de una USB

## Tipo de modo

dentro de los permisos de cada archivo son de 3 grandes partes que son:

1. duenio
2. grupo (compartido entre varios usuarios)
3. world (mundo u otros, aquellos que no son duenios o grupo)

Existen 3 tipos de permisos
r - read
w - write
x - execute

cuando asignamos un permiso, lo encendemos, se le asigna un 1, en este slide los permisos son:

duenio: r - 1, w - 1, x - 1
grupo: r - 1, w - 0, x - 1
world: r - 1, w - 0, x - 1

Como son 3 permisos, la representacion se pueden hacer en trail bits o sistema octal, y los permisos los podemos mostrar mediante un modo octa. Con esos bits, como seria su represnetacion en modo octa?

## propuesta de solucion

Permiso Octal Significado
--- 0 Sin permisos
--x 1 Solo ejecución
-w- 2 Solo escritura
-wx 3 Escritura y ejecución
r-- 4 Solo lectura
r-x 5 Lectura y ejecución
rw- 6 Lectura y escritura
rwx 7 Lectura, escritura y ejecución

Cuando aplicas permisos a un archivo o directorio, se utilizan tres números octales, uno para cada categoría (usuario, grupo, y otros). Por ejemplo:

rwxr-xr-x:
Usuario (u): rwx = 7
Grupo (g): r-x = 5
Otros (o): r-x = 5
Notación Octal Completa: 754

rw-r--r--:
Usuario (u): rw- = 6
Grupo (g): r-- = 4
Otros (o): r-- = 4
Notación Octal Completa: 644

rwx------:
Usuario (u): rwx = 7
Grupo (g): --- = 0
Otros (o): --- = 0
Notación Octal Completa: 700

## Modo simbolico

se pueden asignar permisos tacitamente desde la terminal con algunos comandos, y esta asignacion se puede hacer con simbolos que son:

u - solo para el usuario
g - solo para el grupo
o - solo para otros o todo el mundo
a - aplica para todos

# Modificando permisos con la terminal

Existen diferentes tipos de ususarios y los podemos cambiar ocn la terminal como el usuario root que tiene privilegios para hacer de todo pero nencesitamos saberlo manejar de manera adecuada.

## Manejo de permisos con nuestr usuario y usuario root

```sh

mkdir sandbox

> mitexto.txt
// para crear archivo de texto

# para procesar texto
cat > mitext.txt

y ctrl + d para dejar de escribir

cat mitexto.txt

# root@DESKTOP-JGJI4A4:~/terminal/sandbox# > mitext.txt && ls
# mitext.txt
# root@DESKTOP-JGJI4A4:~/terminal/sandbox# cat > mitext.txt
# Hola, esto es la creacion de texto desde la terminal para modificar un archivo
# root@DESKTOP-JGJI4A4:~/terminal/sandbox# cat mitexto.txt
# cat: mitexto.txt: No such file or directory
# root@DESKTOP-JGJI4A4:~/terminal/sandbox# cat mitext.txt
# Hola, esto es la creacion de texto desde la terminal para modificar un archivo
# root@DESKTOP-JGJI4A4:~/terminal/sandbox#

// para ver los permisos dentro del archivo usamos
ls -l

# ls -l
# total 4
# -rw-r--r-- 1 root root 79 Sep 13 13:32 mitext.txt

/ para cambiar los permisos, usamos
chmod 755 mitext.txt

/ y para valdiar que se otorgaron los permisos
ls -l

# total 4
# -rwxr-xr-x 1 root root 79 Sep 13 13:32 mitext.txt

/ vamos a quitarle los permisos de letura pero solo al usuario y de modo simbolico

chmod u-r mitext.txt
ls -l

chmod u-r mitext.txt && ls -l
# total 4
# --wxr-xr-x 1 root root 79 Sep 13 13:32 mitext.txt

cat mitext.txt
# cat mitext.txt
# Hola, esto es la creacion de texto desde la terminal para modificar un archivo

/ en teoria deberia de quitar los permisos de read pero no lo hizo

# para devolver los permisos

chmod u+r mitext.txt && ls -l && cat mitext.txt
# total 4
# -rwxr-xr-x 1 root root 79 Sep 13 13:32 mitext.txt
# Hola, esto es la creacion de texto desde la terminal para modificar un archivo

# para modificar permisos de una forma mas avanzada, para asignar diferentes permisos en una sola ejecucion. sobre escribe los permisos, no los complementa
chmod u-x,go=w mitext.txt && ls -l && cat mitext.txt
# total 4
# -rw--w--w- 1 root root 79 Sep 13 13:32 mitext.txt
# Hola, esto es la creacion de texto desde la terminal para modificar un archivo
```

ahora veremos como cambiar de usaurio

```sh

# para saber quienes somos:
whoami
# root

# otro camando para tener el uid, el nombre de nuestro usuario que puede ser 1000 o 500, y nos da info extra de a que gurpos llega a pertenecer
id
# uid=0(root) gid=0(root) groups=0(root),999(docker)

# no veremos todos porque podria ser un curso aparte

# para cambiarnos a un usuario, usaremos
su root
# su root
# root@DESKTOP-JGJI4A4:~/terminal# whoami
# root

pwd
# pwd
# /root/terminal

ls -l
# total 4
# -rw-r--r-- 1 root root  0 Sep 13 13:50 codebars
# -rw--w--w- 1 root root 79 Sep 13 13:32 mitext.txt

# para obtener permisos de root
sudo rm rootfile
```

# variables de entorno

tu shell tiene una configuracion y difernetes valores de sistema que se pueden ingresar por variables de entorno, hay variables de entorno que son esenciales para la configuracion del sistema.

Exploraremos para poderlas configurar, etc, como los alias, haremos algunas configuraciones para que se queden de manera permanente.

Antes, veremos los links simbolicos que son un tipo de archiv que hacen referencia a un lugar

```sh
ln -s tost to

# que es un link simbolico es un acceso directo desde la terminal
# tiene todos los permisos pero son simbolicos

total 60
-rw-r--r-- 1 root root 19578 Sep 13 13:58 README.md
-rw-r--r-- 1 root root    60 Sep 10 12:28 error.txt
drwxr-xr-x 2 root root  4096 Sep 13 10:15 holi
-rw-r--r-- 1 root root    29 Sep 10 12:35 input.txt
drwxr-xr-x 6 root root  4096 Sep 10 12:21 new
-rw-r--r-- 1 root root   401 Sep 10 13:45 output.txt
drwxr-xr-x 2 root root  4096 Sep 13 13:53 sandbox
drwxr-xr-x 2 root root  4096 Sep 13 10:27 test
lrwxrwxrwx 1 root root     4 Sep 13 13:59 to -> tost
drwxr-xr-x 3 root root  4096 Sep  9 22:04 tost
-rw-r--r-- 1 root root     0 Sep 10 13:45 tsx.txt
drwxr-xr-x 3 root root  4096 Sep  9 22:07 tust
-rw-r--r-- 1 root root   169 Sep 10 13:50 vaca.txt

# pero no tienen permisos
# probaremos yendo

cd to

```

Ahora si, las variables de entorno

```sh
printenv
# imprime las variables de entorno

SHELL=/bin/bash
# etc
LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:

# como podemos imprimir una variable de entorno

echo $HOME
# root@DESKTOP-JGJI4A4:~/terminal# echo $HOME
# /root

# incluso puede servir como comando:
cd $HOME
# root@DESKTOP-JGJI4A4:~#

# puede ser util para configurar una ruta en especifica

# otra ruta es PATH
echo $PATH
# path tiene todas las rutas donde se encuentran los binarios que ejecutan nuestro sistema
# esta variables es importante porque al instalar nuevos binarios hay distitnos manejadores de paquetes, puede ser con apt, ect, node, npm
# /root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin

# lo que hacen los manajadores es ir traer un repo, insatalar algun binario per o no todas las veces la ruta donde se encuentran los binarios, normalmente nos piden de donde se encuentren los bianarios, hay que agregarlos a la variable path

# como modificar las variables de entorno y como concatenar path,
```

Como modificar las variables de entorno

```sh
ls -la
# -rw-r--r--   1 root root  3392 Nov 22  2023 .bashrc
# es ahi donde se encuentra la configuracion de bash

# zsh para bash

# con VSC podemos abrir
code .bashrc


# para modificar variable de entorno
PLATZI_MESSAGE='Hola amigos'

# para volver a cargar bash
bash

# root@DESKTOP-JGJI4A4:~# bash
# root@DESKTOP-JGJI4A4:~# echo $PLATZI_MESSAGE
# Hola amigos

# y alias nuevo ya esta configurado
ll

# drwx------ 117 root root  4096 Sep 12 21:57 ./
# drwxr-xr-x  35 root root  4096 Sep 13 07:53 ../
# -rw-r--r--   1 root root   192 Nov 17  2023 .angular-config.json
# lrwxrwxrwx   1 root root    22 Mar 30 23:05 .aws -> /mnt/c/Users/DELL/.aws/
# lrwxrwxrwx   1 root root    24 Mar 30 23:05 .azure -> /mnt/c/Users/DELL/.azure/

# ahora veremos echo path
echo $PATH

// dentro de .bashrc

PLATZI_MESSAGE='Hola amigos'

PATH=$PATH:/root/terminal/bin

// dentro de la terminal

PATH=$PATH:/root/terminal/bin
# root@DESKTOP-JGJI4A4:~/terminal# bash
# root@DESKTOP-JGJI4A4:~/terminal# echo $PATH
# /root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/root/terminal/bin

sirve para abreviar alias
como los alias de git

```

# Comandos de busqueda

Nos ayuda a encontrar archivos o directorios, dependeiendo de su extension, nombre, donde se encuentran, etc, es muy poderoso para encontrar archivos .log que recopilan la informacion de un archivo en ejecucion, como en google chrome para saber que paginas visitas, create show, pueden ser molestos y despues se deben borrar.

```sh
which
# nos ayuda a encontrar la ruta de nuestros binarios

which cd
# busca en todoa la ruta del path para encontrar un binario pero no lo encontro porque es una utilidad del bash

which code
# dice donde esta alocado
#  which code
# /mnt/c/Users/DELL/AppData/Local/Programs/Microsoft VS Code/bin/code

# ojo, solo funciona en terminal de ubuntu no en la terminal de vsc

which obs
# para grabar pantalla
# tampoco funciono

find
# find nos permite encontrar un archivo y lo primero que debemos poner es la ruta donde comenzaremos a buscar este archivo como en

# desde home
find ./ -name file

# ./penta/node_modules/@babel/core/lib/transformation/file
# ./.rustup/toolchains/stable-x86_64-unknown-linux-gnu/share/doc/rust/html/rust-by-example/std_misc/file
# ./curso-s-practico/web/node_modules/@babel/core/lib/transformation/file
# ./curso-s-practico/web/node_modules/react-scripts/node_modules/@babel/core/lib/transformation/file

# lo importante es que puede usar wild cards como en
find ./ -name *.txt

# GAL.txt
# ./platzi-nextjs/node_modules/next/dist/compiled/@edge-runtime/primitives/abort-controller.js.LEGAL.txt
# ./platzi-nextjs/node_modules/semantic-ui-react/dist/umd/semantic-ui-react.min.js.LICENSE.txt
# ^C

# podemos combinarlo con less y el pipe operator

find ./ -name *.txt | less

# ./curso-rn-expo/node_modules/@babel/regjsgen/LICENSE-MIT.txt
# ./curso-rn-expo/node_modules/json-schema-deref-sync/LICENSE.txt
# ./curso-rn-expo/node_modules/whatwg-url/LICENSE.txt

# otro modificador de find es buscar por tipes
# files solo archiv
# d solo directorios
find ./ -type fd
find ./ -type d
find ./ -type f

find ./ -type d -name

find ./ -type d -name new

# root@DESKTOP-JGJI4A4:~/terminal# find ./ -type d -name new
# ./new

# vamos a comenar a buscar nuestros logs
find ./ -type f -name *.log

# ./blogeek-platzi/node_modules/spdx-exceptions/test.log
# ./.docker/desktop/log/host/docker-desktop-user-distro.log
# ./curso-s-practico/web/node_modules/nwsapi/dist/lint.log
# ./curso-s-practico/web/node_modules/simple-swizzle/node_modules/is-arrayish/yarn-error.log
# ./curso-s-practico/solana-movies/.anchor/test-ledger/validator-1690409914964.log
# ./curso-s-practico/solana-movies/.anchor/test-ledger/rocksdb/000055.log
# ./curso-s-practico/solana-movies/.anchor/program-logs/Fg6PaFpoGXkYsidMpWTK6W2BeZ7FEfcYkg476zPFsLnS.solana_movies.log
# ./curso-intro-react/project/node_modules/nwsapi/dist/lint.log
# ./.cache/com.vercel.cli/package-updates/vercel-latest.log
# ^C

# como encontrar archivos por tamanio, sin importar el tipo de archivo

find ./ -size 20M

#  find ./ -size 20M
# ./.yarn/berry/cache/next-npm-13.5.6-306005c39c-8.zip
# ./.local/share/solana/install/releases/1.16.4/solana-release/bin/solana-tokens
# ./.cargo/git/checkouts/anchor-bf03d42499b9267c/b7e91d4/tests/auction-house/deps/metaplex/.git/objects/pack/pack-af17eb4d6edafd6b098db14bc8bcbd6ed06f1c5d.pack

whereis
# Este comando localiza los ficheros binarios, fuentes y páginas del manual de un programa

```

existe otro paramaetro llamado 'exec', que una vez que encontramos un archivo, el 'exec' los ejecutara, como por ejemplo, los node modules para que se puedan elimnar de tus archivos.

## reto de la clase

buscar todos los archivos txt, guarda el output del archivo en mis documentos .txt, y que con echo despliege: archivos guardados exitosamente.

```sh

find ./ -name *.txt | less | tee misdocumentos.txt && echo 'Archivo Guardado con exito'

# codigo corregido
find ./ -name "*.txt" | less | tee misdocumentos.txt && echo 'Archivo Guardado con éxito'


# comando base para el ejercicio
# ls -lh | less | tee output.txt

```

# Uso del comando grep

Nos permite encontrar coincidencia s de una busqueda dentro de cualquier texto como por ejemplo, un stdo.

usaremos grep para encontrar coincidencias en el archivo movies.csv

```sh

# encontrar todas las peliculas con la palabra towers, dentro del archivo x
# el primer parametro es una expresion regular, que es una herramienta versatil para hacer busquedas
grep Towers movies.csv

# grep Towers movies.csv
# 108583,Fawlty Towers (1975,Comedy,-1980,1,54
# 5952,"Lord of the Rings: The Two Towers, The",Adventure|Fantasy,2002,4,81

# ahora vamos encontrar todas las lineas o coincidencias que tengan the en movies.csv

grep the movies.csv
# pero no tenemos ningun the que sea al inicio de manera general
# 5002,Fritz the Cat,Animation,1971,3,79
# 5569,"Last House on the Left, The",Crime|Horror|Thriller,1971,2,53
# 6666,"Discreet Charm of the Bourgeoisie, The (Charme discret de la bourgeoisie, Le)",Comedy|Drama|Fantasy,1971,1,96
# 26271,Lady Sings the Blues,Drama|Musical,1972,4,82
# 2531,Battle for the Planet of the Apes,Action|Sci-Fi,1973,2,94
# 6230,Bang the Drum Slowly,Drama,1972,1,60
# 6613,"Day of the Dolphin, The",Drama,1973,5,56
# 7482,Enter the Dragon,Action|Crime,1973,8,100
# 7889,Pat Garrett and Billy the Kid,Western,1973,10,90

# por tanto haremos la busqueda case sensitive, las busqueadas tienden a ser case sensitive para eso agregamos

# con la opcion -i se agrega el ignore case sensitive
grep -i the movies.csv
# asi encontramos todas las coincidencias incluso las que empiezan con The

# 159858,The Conjuring 2,Horror,2015,3,84
# 159972,Approaching the Unknown,Drama|Sci-Fi|Thriller,2016,10,52
# 160563,The Legend of Tarzan,Action|Adventure,2016,1,50
# 160565,The Purge: Election Year,Action|Horror|Sci-Fi,2015,6,96
# 161336,Author: The JT LeRoy Story,Documentary,2015,3,61
# 161918,Sharknado 4: The 4th Awakens,Action|Adventure|Horror|Sci-Fi,2016,10,51
# 163949,The Beatles: Eight Days a Week - The Touring Years,Documentary,2016,6,82

grep -i the movies.csv | less

# si quiero saber el numero de ocurrencias usaremos
grep -c -i the movies.csv
# grep -c -i the movies.csv
# 2912

# o solo con minuscula

grep -c the movies.csv
# grep -c the movies.csv
# 1013

# ahora encontraremos a todas las peliculas que no coincidan, ignorando si empiezan o no con mayuscual
grep -vi the movies.csv

# esto lo guardaremos en un archivo

grep -vi the movies.csv > sinthe.txt && ls && cat sinthe.txt

# se puede hacer un ls y pasarlo con un grep

# tambiern veremos el comando wc, que sirve para saber cuantas palabras hay

# linea | caracteres| numero de bits
wc movies.csv
# wc movies.csv
# 9126  30006 477779 movies.csv

# tiene -l que cuenta el numero de lineas.
wc -l movies.csv
# 9126 movies.csv

# tiene -w que cuenta las palabras.
# wc -w movies.csv
30006 movies.csv

# -c da el numero de bit
wc -c movies.csv
# 477779 movies.csv

```

usa expresiones regulares que sirven para la busqueda, aqui el enlace para el curso.

https://platzi.com/cursos/expresiones-regulares/

y grep nos puede servir si sabemos que hemos puesto una linea en especifico y no recordamoes en donde la hemos puesto o como el log, para filtrar todos los errores.

de hecho hay libros enteros para especialziarse en el uso de grep