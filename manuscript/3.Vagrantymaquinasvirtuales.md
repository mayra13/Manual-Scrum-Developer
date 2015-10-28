# 3 Vagrant y maquinas virtuales

Cuando se está desarrollando en una máquina propia que no es de la oficina y los integrantes del proyecto tienen preferencias por alguna tecnología (sistema operativo, base de datos etc), puede generar problemas de configuración y al realizar cambios en el repositorio de código, por lo cual utilizar una máquina virtual es una buena solución para evitar este tipo de conflictos de configuración.
Vagrant es una herramienta para la creación y configuración de entornos de desarrollo virtuales.
Está disponible para Linux, Mac OS X, Windows, y otras plataformas.

## 3.1 Instalación de Vagrant en Windows
Descargar el paquete de instalación y ejecutarlo, esta instalación no difiere a las instalaciones normales de Windows, se siguen los pasos que aparecerán en la pantalla.
Es necesario descargar la Version 1.7.

__NOTA:__ Descargar Putty si el sistema operativo es Windows. Putty no se configura en  la instalación, se ejecuta hasta que utilizamos el comando “vagrant up” ( que será un poco más adelante) y se realiza la configuración. 

## 3.2 Instalación de Vagrant en Linux
Para la instalación de vagrant desde consola teclear el siguiente comando:

    `sudo apt-get install vagrant`

Para desechar la máquina virtual cruda, sal de la sesión SSH y ejecuta el siguiente comando:

    `vagrant destroy`

## 3.3 Instalación de Vagrant en Mac OS
Para mayor información sobre la máquina virtual Vagrant  para MAC OS pueden consultar los siguientes links:
[Enlace 1][1], [Enlace 2][2]

 [1]: http://cdn.oreillystatic.com/oreilly/booksamplers/9781449335830_sampler.pdf
 [2]: http://codehero.co/como-instalar-y-configurar-vagrant/

## 3.4 Instalación de VirtualBox en Windows
Windows
Para realizar la instalación descarga el paquete en la versión 5.0.4 y sigue los pasos normalmente en la siguiente liga:
[Enlace 3][3]

[3]: https://www.virtualbox.org/wiki/Downloads

![Instalación de VirtualBox](images/virtualboxparawindows.png)

__NOTA:__ VirtualBox no corre en Windows con la versión 4.3, descargar la versión 5.

## 3.5 Instalación de VirtualBox en Linux
Se puede realizar la descarga del paquete en el siguiente link:
[Enlace 1][1], [Enlace 2][2]

[1]: https://www.virtualbox.org/wiki/Downloads
[2]: https://www.virtualbox.org/wiki/Linux_Downloads

Ó realizar la instalación desde consola con el siguiente comando:
    
    `sudo apt-get install virtualbox`

![Correcta instalacion de virtualBox](images/Correctainstalacionvirtualbox.png)

## 3.6 Instalación de VirtualBox en Mac OS

Después de haber realizado la instalación de Vagrant y VirtualBox desde la consola realiza lo siguiente:

* Crear una carpeta que se utilizará para desarrollar los ejercicios del curso en la ruta donde regularmente se trabaja.

    `mkdir scrum_developer`

![](images/mkdircrearcarpeta.png)

* El instructor te proporcionará un archivo con el nombre “python.box” colocar dentro de la carpeta que se creó.

![](images/cdscrumdeveloper.png)

* Ejecuta el siguiente comando para que Vagrant reconozca que existe una máquina virtual.

    `vagrant box add developer developer.box`

![](images/reconozcamaquinavirtual.png)

* Ejecutar la máquina virtual con el siguiente comando.

    `vagrant init developer`

![](images/correrlamaquinavirtual.png)

* Levantar la máquina virtual (Si tu sistema operativo es Windows, pasar al sub tema __“Configuración de Putty”__)
    
    `vagrant up`

![](images/Levantarmaquinavirtual.png)

* Realizar la conexión a la máquina virtual. Si tu sistema operativo es Windows es momento de configurar Putty ya que este SO no puede ejecutar el comando ssh.

    `vagrant ssh`

![](images/vagrantssh.png)

## 3.7 Configuración de Putty. 

Configurar Putty de la siguiente manera:

1.-Al teclear el comando:

    `vagrant up` 

te mostrará la siguiente pantalla:

![](images/vagrantupputty.png)

2.-Ejecutar el programa Putty y configurarlo con los datos del paso anterior.

![](images/programaputty.png)

3.-Con los datos ingresados en Putty, te pedirá usuario: __vagrant__ y contraseña: __vagrant__.

![](images/usuarioputty.png)

4.-Si la configuración fue exitosa te aparecerá lo siguiente en la consola.

![](images/conexitosaputty.png)

* Entrar a la raíz de la máquina virtual (lo que se guarde en este directorio, se guardará tanto en local como en la máquina virtual).
 
    `cd /vagrant`

![](images/cdvagrant.png)

En la siguiente tabla se mencionan los comandos que se utilizan en este tema (no van en el orden que se ejecutan)

| Definición                                      |                     Comando                       |
| :-------:                                     |                      :------:                          |
|Crear archivo central para la configuración del proyecto |$mkdir nombre_de_la_carpeta                 |
|Entrar a la carpeta | $cd nombre_de_la_carpeta |
|Crea el archivo de configuración de Vagrant | $vagrant init nombre_de_la_maquina_virtual |
|Levantar el ambiente virtual | $vagrant up |
|Para realizar la conexión a la máquina virtual (en Windows la conexión se realiza desde Putty, checar nota al final del tema) | $vagrant ssh|
|Cerrar | $exit |
|Apagar la máquina virtual | $vagrant halt |
|Vagran reconozca que existe un archivo que define una máquina virtual| $vagrant box add nombre_de_la_maquinavirtual scrum_developer.box |
|Lo que se ejecute con este comando se aplicará en la máquina virtual y en la máquina física | $/vagrant <> |
|Entrar al directorio raíz | cd /vagrant |
|Devuelve la ruta en la que se está situado | $pwd |
| Descargar archivo desde un servidor | $vagrant box add scrum_developer http://10.13.4.7\0:8000/scrum_developer.box |
| Muestra la versión instalada | python --version |

Tabla: Comandos a utilizar para vagrant
