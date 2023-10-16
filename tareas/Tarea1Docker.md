# Sara Lamas Diz			 ASIR 2

La siguiente práctica es una lista de tareas que tenéis que hacer. Por cada tarea tenéis que ir poniendo los comandos utilizados y, brevemente, describir el proceso.
Utilizaremos la imagen de Ubuntu (la última). Usa Visual Studio Code y Docker junto con esta imagen para seguir las siguientes instrucciones:


### 1. **Descarga la imagen 'ubuntu’ y comprueba que está en tu equipo. Para ello lanzamos estos comandos en la terminal para descargarla:**

        docker run hello-world

        docker search ubuntu 

        docker pull ubuntu:latest

    Para ejecutarla ponemos:

        docker run ubuntu

    Para ver si existe ponemos:

        docker images


### 2. **Crea un contenedor sin ponerle nombre. ¿Está arrancado? Obtén el nombre.**

    Usamos

        “docker run”

    para crearlo y directamente se pone un nombre aleatorio por defecto.


### 3. **Crea un contenedor con el nombre 'ubu1'. ¿Cómo puedes acceder a él?.** 

    Se crea con

        “docker run -it --name ubi1 ubuntu bash”

    y al crearlo ya entramos directamente en él.


### 4. **Comprueba que ip tiene y si puedes hacer un ping a google.com.**

    Primero debemos instalar los paquetes de net tools y de ping para poder hacerlo:

        apt update

        apt-get install net-tools

        apt-get update && apt-get install -y iputils-ping

        ifconfig

    obtenemos “inet 172.17.0.2  netmask 255.255.0.0  broadcast 172.17.255.255”

        ping google.com

### 5. **Crea un contenedor con el nombre 'ubu2'. ¿Puedes hacer ping entre los contenedores?**

    Abrimos otra ventana de terminal y creamos el contenedor con: 

        docker run -it --name ubi2 ubuntu bash

    También debemos instalarle los paquetes de net tools y ping:

        apt update

        apt-get install net-tools

        apt-get update && apt-get install -y iputils-ping

        ifconfig

    Hacemos ping desde docker ‘ubi1’ a ‘ubi2’ con “ping 172.17.0.3”


### 6. **Sal del terminal, ¿qué ocurrió con el contenedor?**

 Se cerró pero no se borró


### 7. **¿Cuánta memoria en el disco duro ocupaste? ¿Hay alguna herramienta de docker para calcularlo?**

Se ocuparon pocos MB.

se calcula con el comando “docker stats”


### 8. **¿Cuanta RAM ocupan los contenedores? Crea cuantos contenedores necesites para calcularlo.**

con ‘ubi1’ ocupé 65,14MiB

     