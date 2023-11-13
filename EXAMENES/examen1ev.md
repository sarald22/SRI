
### 1. Explica métodos para 'abrir' una consola/shell a un contenedor que se está ejecutando

            'docker exec -it nombre_contenedor /bin/bash'

- sirve para ejecutar comandos dentro del contenedor como si fuera una consola
#
            'docker attach nombre_contenedor'

- con él te puedes conectar a un contenedor en la sesión que se está realizando y para conectarte con sus entradas y salidas. Para salir puedes usar CTRL+Q
#
            'docker run -it nombre_imagen_contenedor /bin/bash'

- para abrir una sesion interactiva con el contenedor.




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




### 3. ¿Cómo sería un fichero docker-compose para que dos contenedores se comuniquen entre si en una red solo de ellos?

Como el mostrado en el siguiente enlace:
            https://github.com/sarald22/SRI/blob/main/EXAMENES/docker-compose.yml 

### 4. ¿Qué hay que añadir al fichero anterior para que un contenedor tenga la IP fija?



### 5. ¿Que comando de consola puedo usar para saber las ips de los contenedores anteriores? Filtra todo lo que puedas la salida.



### 6. ¿Cual es la funcionalidad del apartado "ports" en docker compose?



### 7. ¿Para que sirve el registro CNAME? Pon un ejemplo



### 8. ¿Como puedo hacer para que la configuración de un contenedor DNS no se borre si creo otro contenedor?



### 9. Añade una zona tiendadeelectronica.int en tu docker DNS que tenga

    - www a la IP 172.16.0.1
    - owncloud sea un CNAME de www
    - un registro de texto con el contenido "1234ASDF"
    - Comprueba que todo funciona con el comando "dig"
    - Muestra en los logs que el servicio arranca correctamente



10. Realiza el apartado 9 en la máquina virtual con DNS

    - www a la IP 172.16.0.1

    - owncloud sea un CNAME de www

    - un registro de texto con el contenido "1234ASDF"

    - Comprueba que todo funciona con el comando "dig"

    - Muestra en los logs que el servicio arranca correctamente


