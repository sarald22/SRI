
### 1. Conectarse al usuario admin de otra máquina por medio de claves publica y privado

- Si no tenemos instalado SSH, lo instalamos con:

            sudo apt install openssh-client

y lo activamos con:

            sudo systemctl enable ssh

- Una vez instalado y habilitado, ponemos el comando:

            ssh-keygen -t rsa -b 4096

De esta manera generaremos una clave público-privada que aplique seguridad a la conexión.

- Copiamos la clave al otro equipo al que vamos a conectarnos con:

            ssh-copy-id usuario@direccion_ip-destino

- Una vez completada la copia, ya podemos conectarnos con SSH al usuario:

            ssh usuario@direcion_ip_destino


- Para finalizar la sesión usamos el comando "exit"



#
#
### 2. Como configurar el acceso ssh en el GitHub


1. **Generamos claves SSH:** 

```bash
ssh-keygen -t rsa -b 4096 -C "slamasdiz@danielcastelao.org"
```
