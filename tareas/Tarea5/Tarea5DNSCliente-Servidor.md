#### Añade al docker-compose del DNS otro servicio (contenedor) que haga la función de cliente.
#### Utiliza una imágen alpine

#### Instala los paquetes necesarios para poder usar en el cliente los comandos de red del siguiente enlace.
#### Comprueba su uso.

#### Instala, si es necesario, para poder usar el comando 'dig'.

#### Configura el cliente para que su DNS sea el otro contenedor, modificando el resolv.conf o utilizando el fichero docker-compose.yml.

#### Compruébalo con 'dig'.
#### Adjunta el repositorio y completa el Readme con lo realizado (comandos para instalar paquetes y pruebas con 'dig').



1. ## Creamos el archivo docker-compose para levantar el servidor:

![configuraciondockercompose](https://github.com/sarald22/SRI/blob/main/tareas/Tarea5/dockercompose.png)


## y luego el archivo docker del cliente:

![configuraciondockercompose](https://github.com/sarald22/SRI/blob/main/tareas/Tarea5/dockercomposecliente.png)


#

2. ## El resto de archivos de configuracion y de zonas los dejamos igual. Con las mismas redes.

![archivosdns](https://github.com/sarald22/SRI/blob/main/tareas/Tarea5/archivosdns.png)


#

3. ## Para poder usar el comando 'dig' tenemos que instalar los paquetes de herramientas DNS:
            sudo apt install dnsutils

#

4. ## el cliente quedaria asi configurado:

![configuraciondockercompose](https://github.com/sarald22/SRI/blob/main/tareas/Tarea5/dockercomposecliente.png)



5. ## para que todo funcione, debemos poner en las network de nuestros docker la dirección de la Network en bridge del equipo. Vamos al archivo de dicha red y le damos a Inspect. Veremos esto:

![network](https://github.com/sarald22/SRI/blob/main/tareas/Tarea5/network.png)

## como podemos observar, la red es 172.17.0.0/16, por lo que a nuestros docker le tenemos que poner la 172.17.0.0 y la 172.17.0.1.


#

6. ## Ahora, para ver si funciona todo correctamente, solo tenemos que encender el docker con el comando:
            docker-comopse up

![dockerup](https://github.com/sarald22/SRI/blob/main/tareas/Tarea5/dockerup.png)

![dockerupcliente](https://github.com/sarald22/SRI/blob/main/tareas/Tarea5/dockerupcliente.png)


## y nos quedarian asi encendidos:

![servidorencendido](https://github.com/sarald22/SRI/blob/main/tareas/Tarea5/servidorencendido.png)
