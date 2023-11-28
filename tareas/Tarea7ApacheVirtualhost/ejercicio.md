
## Tarea 7: Apache + Virtual Host 

#### Utiliza el repositorio en github del ejercicio anterior
#### Crea un Readme.md para ir documentando los pasos, utiliza esta guía de markdown para la redacción
#
#
#### 1. Añade un DNS al docker-compose (puedes usar el que ya tienes)

- Añadimos el DNS hacia el final del documento, asi como indicamos en la foto:

![contenedordns](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/contenedordns.png)

#
#### 2. Utiliza docker-compose para configurar las IP fijas a los dos contenedores acuerdate de usar los prefijos asir_ en los nombres de los contenedores

- Configuramos las redes individuales de los contenedores:

![contenedor1](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/contenedor1.png)

![contenedor2](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/contenedor2.png)


- Aquí podemos ver que encienden correctamente:

![contenedoresfuncionando](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/contenedoresfuncionando.png)

![dockercompose](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/contenedores.png)


#
#### 3. El DNS tiene que resolver dos dominios a la ip del apache, por ejemplo:
####        - www.fabulasoscuras.com
####        - www.fabulasmaravillosas.com

- Una vez que nos funciona correctamente cada contenedor, seguimos configurando el dns y los sitios
- Vamos a la carpeta "confApache" y creamos las conf de los 2 sitios, asi como se muestra en la imagen:

![conffabulas](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/conffabulas.png)


- Asimismo, en el archivo 'named.conf.local' de la carpeta conf, debemos poner las zonas de los 2 dominios:

![conflocal](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/conflocal.png)


- El archivo 'named.conf' debe quedar asi:

![namedconf](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/namedconf.png)



#
#### 4. Prueba a utilizar la directiva DirectoryIndex

Entramos en la carpeta 'confApache' y en 'extra' metemos la conf de las zonas de los 2 dominios:

- Conf de fabulas maravillosas ya creada en la carpeta confApache

![confmaravillosas](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/confmaravillosas.png)


- Conf de fabulas maravillosas ya creada en la carpeta confApache

![confoscuras](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/confoscuras.png)


- Conf de las fabulas en la carpeta confApache/extra

![confapache](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/confapache.png)


#
#### 5. Configura dos virtual-host separados para cada dominio en el mismo puerto (80)

- Al añadirlos en la carpeta mencionada anteriormente, ya se configuran los 2 por separado. Basta con crear el archivo ".conf" de cada sitio con sus respectivos puertos (80) y los directorios:


![confmaravillosas](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/confmaravillosas.png)

![confoscuras](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/confoscuras.png)


- Una vez creados, reiniciamos apache con "sudo systemctl restart apache2" para aplicar las configuraciones. Y ya podemos iniciar nuestro docker con "docker-compose up", o reiniciarlo, con "docker-compose restart":

![apachereiniciado](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/apachereiniciado.png)



#
#
- Aqui podemos ver el funcinamiento de los host:

![index](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/index.png)

![index2](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/index2.png)

![enlace](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/enlace.png)

