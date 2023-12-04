#### Configura un servidor de DHCP, en la máquina virtual de linux.

#### El DHCP, servirá la ip a otra máquina que estén en la misma red (red interna de VirtualBox); para probarlo tendras que levantar otra máquina virtual.

#### Pasos:

1. **Instalar paquete isc-dhcp-server**

![instalacion] (https://github.com/sarald22/SRI/blob/main/tareas/Tarea8/imagenes/instalacion.png)

2. **Editar para una configuración básica /etc/dhcp/dhcpd.conf**



3. **Editar para configurar la interfaz de red /etc/default/isc-dchp-server**



4. **Declarar una subnet 172.16.0.0/16**



5. **Arranca el servicio con systemctl**



6. **Comprueba el servicio con "systemctl status"**



7. **Prueba con el cliente que se le asigna un ip en el rango**



8. **Declarar una asignación por mac fija a 172.16.0.5**



9. **Prueba con otro cliente que se le asigna la ip fija**



