
## Tarea 7: Apache + Virtual Host 

#### 1. Utiliza el repositorio en github del ejercicio anterior
#### 2. Crea un Readme.md para ir documentando los pasos, utiliza esta guía de markdown para la redacción
#
#
#### 3. Añade un DNS al docker-compose (puedes usar el que ya tienes)

- Añadimos el DNS hacia el final del documento, asi como indicamos en la foto:

![dockercompose](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/dockertarea7.png)

#
#### 4. Utiliza docker-compose para configurar las IP fijas a los dos contenedores acuerdate de usar los prefijos asir_ en los nombres de los contenedores

- Configuramos las redes individuales de los contenedores:

![dockercompose](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/dockertarea7.png)


- Aquí podemos ver que encienden correctamente:

![dockercompose](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/dockerfuncionando.png)

![dockercompose](https://github.com/sarald22/SRI/blob/main/tareas/Tarea7ApacheVirtualhost/imagenes/contenedores.png)

#
#### 5. El DNS tiene que resolver dos dominios a la ip del apache, por ejemplo:
####        - www.fabulasoscuras.com
####        - www.fabulasmaravillosas.com


#
#### 6. Prueba a utilizar la directiva DirectoryIndex


#
#### 7. Configura dos virtual-host separados para cada dominio en el mismo puerto (80)

