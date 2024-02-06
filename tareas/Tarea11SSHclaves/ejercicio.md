
### 1. Conectarse al usuario admin de otra máquina por medio de claves publica y privado

- Si no tenemos instalado SSH, lo instalamos con:

            sudo apt install openssh-client

y lo activamos con:

            sudo systemctl enable ssh

- Una vez instalado y habilitado, ponemos el comando:

            ssh-keygen -t rsa -b 4096

![1](https://github.com/sarald22/SRI/blob/main/tareas/Tarea11SSHclaves/imagenes/1.png)

De esta manera generaremos una clave público-privada que aplique seguridad a la conexión.

- Copiamos la clave al otro equipo al que vamos a conectarnos con:

            ssh-copy-id usuario@direccion_ip-destino

- Una vez completada la copia, ya podemos conectarnos con SSH al usuario:

            ssh usuario@direcion_ip_destino


- Para finalizar la sesión usamos el comando "exit"



#
#
### 2. Como configurar el acceso ssh en el GitHub

- **Generamos claves SSH:** 

            ssh-keygen -t rsa -b 4096 -C "slamasdiz@danielcastelao.org"

![2](https://github.com/sarald22/SRI/blob/main/tareas/Tarea11SSHclaves/imagenes/2.png)


##
- **Añadimos la clave SSH al SSH-agent:** esto sirve para que el agente pueda administrar las claves:

            ssh-add ~/.ssh/id_rsa

![3](https://github.com/sarald22/SRI/blob/main/tareas/Tarea11SSHclaves/imagenes/3.png)

#
- **Copiamos la clave pública:**

            pbcopy < ~/.ssh/id_rsa.pub

![4](https://github.com/sarald22/SRI/blob/main/tareas/Tarea11SSHclaves/imagenes/4.png)


- **Ahora la agregamos a Github:** iniciamos sesión en Github y vamos a la configuración del perfil:

    - En el menú de la izquierda, entra en "SSH and GPG keys" y clica en "New SSH key" o "Add SSH key".

    - En "Title" le ponemos un nombre a la clave SSH y en "key" pegamos la clave pública que copiamos.

    - Guardamos cambios en "Add SSH key".


Una vez completado todo esto, ya tendríamos el SSH correctamente configurado con nuestra cuenta de GitHub.
