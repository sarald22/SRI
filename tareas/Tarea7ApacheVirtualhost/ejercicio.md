
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

![dockercompose](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/dockerfuncionando.png)

![dockercompose](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/contenedores.png)


#
#### 3. El DNS tiene que resolver dos dominios a la ip del apache, por ejemplo:
####        - www.fabulasoscuras.com
####        - www.fabulasmaravillosas.com

- Una vez que nos funciona correctamente cada contenedor, seguimos configurando el dns y los sitios
- Vamos a la carpeta "confApache" y creamos las conf de los 2 sitios, asi como se muestra en la imagen:

![confsitios](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/conffabulas.png)


#
#### 4. Prueba a utilizar la directiva DirectoryIndex


#
#### 5. Configura dos virtual-host separados para cada dominio en el mismo puerto (80)


![confmaravillosas](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/confmaravillosas.png)

![confoscuras](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/confoscuras.png)

![confapache](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/confapache.png)
