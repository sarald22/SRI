
### Utiliza una máquina virtual Ubuntu Server LTS
### Instala bind9 con apt
### Configura las zonas del DNS igual que en docker
### Comprueba (en el propio servidor) con el comando 'dig' que el servidor funciona



1. Instalamos en la maquina virtual bind9 con el comando 
'''
sudo apt install bind9
'''
![foto1](https://github.com/sarald22/SRI/blob/main/tareas/Tarea6/Screenshot_20231107_180250.png)


2. ponemos el comando 'systemctl status bind9' para ver su estado y si está arrancado o no.
![foto2](https://github.com/sarald22/SRI/blob/main/tareas/Tarea6/Screenshot_20231107_180349.png)


3. luego entramos a la carpeta /etc/bind y veremos las configuraciones de nuestro servidor DNS.
![foto3](https://github.com/sarald22/SRI/blob/main/tareas/Tarea6/Screenshot_20231107_164905.png)


4. entramos a cada documento y le cambiamos la configuración del servidor.
![foto4](https://github.com/sarald22/SRI/blob/main/tareas/Tarea6/Screenshot_20231107_180435.png)


5. cuando acabemos probamos si el servidor funciona con el comando 'dig ns.asircastelao.int.' 
    y vemos si envia paquetes o no.
![foto5](https://github.com/sarald22/SRI/blob/main/tareas/Tarea6/Screenshot_20231107_165558.png)









