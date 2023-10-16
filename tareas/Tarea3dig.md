Tarea: interactuando con 'dig'


1. Realiza una consulta “dig danielcastelao.org” e identifica el significado de cada parte
de la respuesta (IN, CNAME, A, QUERY SECTION, ANSWER SECTION, AUTHORITY SECTION,etc)

<image src="/ejercicios/ej1.jpeg" alt=" ejercicio 1">

IN →900
CNAME →danielcastelao.ORG
A →178.211.133.37
QUERY SECTION → 1
ANSWER QUESTION → 1
AUTHORITY SECTION → 0


2. Realiza las consultas de nombres: moodle.danielcastelao.org, www.danielcastelao.org
¿Diferencias?

<image src="/ejercicios/ej2.jpeg" alt=" ejercicio 2">
<image src="/ejercicios/ej2_2.jpeg" alt=" ejercicio 2">




3. Con relación al dominio www.danielcastelao.org, averigua el nombre y dirección IP de
los servidores de DNS autoritativos de dicho dominio. ¿Por qué normalmente suelen ser 2
servidores autoritativos?

<image src="/ejercicios/ej3.jpeg" alt=" ejercicio 3">



4. Realice las consultas de nombres inversas: 130.206.164.68 y de otras direcciones IP que
se te ocurran.


5. ¿A qué servidor DNS estás consultando? ¿Cómo lo puede cambiar sin tocar los
ficheros de configuración del sistema?


6. Obten el registro SOA (Start of Authoriy) del dominio moodle.danielcastelao.org
preguntándoselo al servidor DNS de google, y preguntándoselo directamente al servidor
primario del dominio danielcastelao.org.


7. Consulta la dirección IP de www.elpais.com. ¿Cuánto tiempo almacenará en cache su
DNS local este registro de recurso? Pregunta varias veces a su DNS local por esta dirección.
¿Qué observas en el TTL del registro de recurso?


8. Descubre el TTL de diferentes nombres de dominio de servicios que conozca ¿A qué
se puede deber esas diferencias?


9. Determina el TTL máximo (original) de un nombre de dominio.


10. Averigua cuantas máquinas (diferentes direcciones IP) están detrás del dominio web
www.google.es. ¿Obtiene siempre las mismas y en el mismo orden? ¿Por qué?


11. Pregunta ahora lo mismo a un servidor raíz (por ejemplo J.ROOTSERVERS.NET) y
compruebe en la respuesta si dicho servidor acepta el modo recursivo.


12. Si queremos ver todas las preguntas que hace el servidor de DNS, que opción
tenemos que usar, averigua la dirección IP de www.timesonline.co.uk. ¿Qué pasos ha dado?


13. Utilizando la información disponible a través del DNS determina (nombre y dirección
IP) la máquina o máquinas que actúan como servidoras de correo del dominio
danielcastelao.org.


14. ¿Puedes obtener los registros AAAA de www.facebook.com? ¿A qué corresponden?


