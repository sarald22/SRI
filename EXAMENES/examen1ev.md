
### 1. Explica métodos para 'abrir' una consola/shell a un contenedor que se está ejecutando

            'docker exec -it nombre_contenedor /bin/bash'

- sirve para ejecutar comandos dentro del contenedor como si fuera una consola
#
            'docker attach nombre_contenedor'

- con él te puedes conectar a un contenedor en la sesión que se está realizando y para conectarte con sus entradas y salidas. Para salir puedes usar CTRL+Q
#
            'docker run -it nombre_imagen_contenedor /bin/bash'

- para abrir una sesion interactiva con el contenedor.


#
#

### 2. En el contenedor anterior con que opciones tiene que haber sido arrancado para poder interactuar con las entradas y salidas del contenedor

Puedes abrirlo de varias formas, como lo son:

            docker run -it nombre_imagen_contenedor

- La 'i' mantiene abierta la salida estándar y la 't' asigna una terminal al contenedor.
#
            docker run -d

- Sirve para ejecutar el contenedor en segundo plano. Puedes interactuar con él luego con el comando: 'docker exect -it nombre_contenedor /bin/bash'

#
            docker run -p 'puerto':'puerto' nombre_iamgen

- La 'p' sirve para mapear los puertos del contenedor.
#

            docker run -v nombre_contenedor

- Sirve para montar los volumenes del contenedor desde el host. Por ejemplo:

            docker run -v /etc/bin/asir:/home/servidor/asir httpd


#
#

### 3. ¿Cómo sería un fichero docker-compose para que dos contenedores se comuniquen entre si en una red solo de ellos?

Como el mostrado en el siguiente enlace:

https://github.com/sarald22/SRI/blob/main/EXAMENES/docker-compose.yml 



#
#


### 4. ¿Qué hay que añadir al fichero anterior para que un contenedor tenga la IP fija?

Para hacerlo, podemos eliminar la asignación de puertos porque no haria falta para asignar la IP fija. Tendriamos que añadir en networks las lineas:

            networks:
                bind9_subnet:
                    ipv4_address: 172.28.5.2

pero como ya están escritas, ya no haría falta ponerlas. Es así como se le asigna la IP fija al contenedor.



#
#

### 5. ¿Que comando de consola puedo usar para saber las ips de los contenedores anteriores? Filtra todo lo que puedas la salida.

Puedo usar el comando:

            docker inspect -f '{.Name} - {range .NetworkSettings.Networks}{.IPAddress}{end}' asir_bind9 asir_cliente
 


#
#


### 6. ¿Cual es la funcionalidad del apartado "ports" en docker compose?

Sirve para indicar y mapear los puertos a los que el contenedor y el host deben conectarse. Tendria el formato:

    ports:
      - puerto_del_host:puerto_del_contenedor/protocolo_a_usar

El protocolo es opcional. Puede verse un ejemplo en el docker-compose adjuntado en el ejercicio 3:

https://github.com/sarald22/SRI/blob/main/EXAMENES/docker-compose.yml


#
#


### 7. ¿Para que sirve el registro CNAME? Pon un ejemplo

Es un tipo de registro de DNS.
Significa nombre canónico y hace que un dominio sea un alias para otro. El CNAME generalmente asocia nuevos subdominios con dominios ya existentes de registro A.
Se debe indicar en el archivo de la zona del servidor; un ejemplo de ellos seria:

        buenastardes IN  CNAME   www.danielcastelao.com

Podemos ver otro ejemplo de CNAME en el archivo de zona de nuestro DNS:

https://github.com/sarald22/SRI/blob/main/EXAMENES/zonas/db.asircastelao.int


#
#


### 8. ¿Como puedo hacer para que la configuración de un contenedor DNS no se borre si creo otro contenedor?

Para que no se borre podemos usar los archivos de docker-compose y crear todos los que necesitemos. En ellos debemos añadir los apartados de volumenes, y que se vayan asignando segun vamos haciendo un contenedor nuevo. Por ejemplo:
                volumes:
            - ./conf:/etc/bind
            - ./zonas:/var/lib/bind

Además, a la hora de crear un DNS debemos tener los archivos de conf y de zonas creados:

![fotocarpetas](https://github.com/sarald22/SRI/blob/main/EXAMENES/imagenes/ejericico8.png)
#
Como ejemplo podemos tomar las carpetas adjuntadas en este repositorio:

- carpeta de zonas:

https://github.com/sarald22/SRI/tree/main/EXAMENES/zonas

- carpeta de configuración:

https://github.com/sarald22/SRI/tree/main/EXAMENES/conf


#
#


### 9. Añade una zona tiendadeelectronica.int en tu docker DNS que tenga

- www a la IP 172.16.0.1
- owncloud sea un CNAME de www
- un registro de texto con el contenido "1234ASDF"

![fotozona](https://github.com/sarald22/SRI/blob/main/EXAMENES/imagenes/ejercicio9zona.png)
#

- Comprueba que todo funciona con el comando "dig"

Entramos a la terminal del contenedor de la siguiente manera e introducimos los comandos de dig. Para poder hacerlo primeramente tenemos que instalar los paquetes de dnsutils para poder usar el dig, con 'apt install dnsutils':

![fotozona](https://github.com/sarald22/SRI/blob/main/EXAMENES/imagenes/shelldocker.png)



#
    - dig 172.28.5.1 tiendadeelectronica.int

![foto9](https://github.com/sarald22/SRI/blob/main/EXAMENES/imagenes/digdocker2.png)

#
- Muestra en los logs que el servicio arranca correctamente

Los logs podemos verlos de 2 maneras:

Los que nos salen en la terminal, bien iniciando el contenedor o poniendo el comando 'docker-compose logs asir_bind9_examen':

![foto10](https://github.com/sarald22/SRI/blob/main/EXAMENES/imagenes/encendiendodocker.png)


O yendo al apartado de docker y clicando encima del servidor y dandole a 'view logs': 

![foto10](https://github.com/sarald22/SRI/blob/main/EXAMENES/imagenes/encendido.png)

![foto10](https://github.com/sarald22/SRI/blob/main/EXAMENES/imagenes/logsdocker.png)




#
#
### 10. Realiza el apartado 9 en la máquina virtual con DNS

- www a la IP 172.16.0.1
- owncloud sea un CNAME de www
- un registro de texto con el contenido "1234ASDF"

Debemos ir a la carpeta de bind9 en la maquina y crear un archivo llamando 'db.tiendadeelectronica' y añadir lo mismo que añadimos en el archivo de DNS anterior:

![fotozona](https://github.com/sarald22/SRI/blob/main/EXAMENES/imagenes/maquinazona.png)

Ahora hacemos un 'sudo service bind9 restart' y vemos el estado del DNS con 'sudo systemctl status bind9':

![fotozona](https://github.com/sarald22/SRI/blob/main/EXAMENES/imagenes/bindencendido.png)

#
- Comprueba que todo funciona con el comando "dig"

Ahora en la terminal ponermos los comandos de ejemplo:

    - dig 10.0.2.15 tiendadeelectronica

![fotozona](https://github.com/sarald22/SRI/blob/main/EXAMENES/imagenes/digbind1.png)

#
    - dig @10.0.2.15 tiendadeelectronica

![fotozona](https://github.com/sarald22/SRI/blob/main/EXAMENES/imagenes/digbind2.png)

#
- Muestra en los logs que el servicio arranca correctamente

Podemos usar el comando 'tail', que es para ver las ultimas lineas de un archivo en la terminal:

            tail /var/log/syslog

![fotozona](https://github.com/sarald22/SRI/blob/main/EXAMENES/imagenes/logsbind.png)
