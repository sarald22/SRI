
Para comprobar los log puedes ver el fichero: /var/log/syslog , aunque lo mejor es configurarlo como en la guia

    Utiliza una máquina virtual Ubuntu Server LTS
    Instala bind9 con apt
    Configura las zonas del DNS igual que en docker
    Comprueba (en el propio servidor) con el comando 'dig' que el servidor funciona



1. Instalamos en la maquina virtual bind9 con el comando 'sudo apt install bind9'


2. ponemos el comando 'systemctl status bind9' para ver su estado y si está arrancado o no.


3. luego entramos a la carpeta /etc/bind y veremos las configuraciones de nuestro servidor DNS.


4. entramos a cada documento y le cambiamos la configuración del servidor.


5. cuando acabemos probamos si el servidor funciona con el comando 'dig ns.asircastelao.int.' 
    y vemos si envia paquetes o no.







