# Sara Lamas ASIR2

## Tarea: Docker - Trabajando con volúmenes


1. **Descarga la imagen 'httpd' y comprueba que está en tu equipo.**

  hecho 




2. **Crea un contenedor con el nombre 'asir httpd'.**
   
  - añadimos estas líneas al archivo “docker-compose.yml”

```
      services:
        asir_httpd:
          image: httpd:2.4
          ports:
            - "80:80"
          volumes:
            - /home/asir2/SRI/APACHE/paginas
          container_name: asir httpd
```

  - luego en terminal enviamos este comando, para crear el contenedor:
```
      docker run -dit --name my-apache-app -p 8080:80 -v /home/asir2/SRI/APACHE/paginas:/usr/local/apache2/htdocs/ httpd:2.4
```


3. **Mapea el puerto 80 del contenedor con el puerto 8000 de tu máquina.**

  - Para ello tenemos que poner el siguiente comando, con los peurtos 8000 (el nuestro) y 80 (el del contenedor)

```
       docker run -dit --name my-apache-app -p 8000:80 httpd:2.4
```


4.  **Utiliza bind mount para que el directorio del apache2 'htdocs' este montado un directorio que tu elijas.**
Utiliza -v "$PWD"/htdocs:/usr/local/apache2/htdocs/

  - Debemos poner el siguiente comando con las rutas *"$PWD"/htdocs*   y   */usr/local/apache2/htdocs/*

```
      docker run -dit --name my-apache-app -p 8080:80 -v -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd:2.4
```


5. **Realiza un 'hola mundo' en html y comprueba que accedes desde el navegador.**

  - Abrimos un archivo .html donde tengamos el archivo de docker-compose y le añadimos las líneas:

```
          < html>
              <*h1> hola mundo </h1>
          </html>
```

  - En la barra del navegador ponemos “localhost:8000” y debería aparecernos el texto deseado.



6. **Crea un contenedor 'asir_web1' que use este mismo directorio para 'htdocs' y el puerto 8000**

  - Creamos un documento 'docker-compose.yml' y añadimos las siguientes lineas:

```
        services:
          asir_web1:
            image: httpd:2.4
            ports:
              - "8000:80"
            volumes:
              - /home/asir2/SRI/APACHE/paginas
            container_name: asir_web1
```



7. **Utiliza Code para hacer un hola mundo en html**
  - Ponemos en terminal el comando:

```
        nano tarea1.html
```

  - y escribimos dentro: 

```
          < html>
              < h1> hola mundo </h1>
          </html>
```



8. **Crea otro contenedor 'asir_web2' con el mismo directorio y a otro puerto, por ejemplo 9080.**

  - Añadimos al documento estas lineas:
  
```
        services:
          asir_web2:
            image: httpd:2.4
            ports:
              - "9080:80"
            volumes:
              - /home/asir2/SRI/APACHE/paginas
            container_name: asir_web2
```



9. **Comprueba que los dos servidores 'sirven' la misma página, es decir, cuando consultamos en el navegador:**

  - http://localhost:9080 

 -  http://localhost:8000

sirven



10. **Tienen que salir la misma página web**

  si, sale
