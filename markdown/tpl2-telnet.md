TPL 2 - Aplicaciones 1: Cliente/Servidor - Telnet
=================================================

**Fecha de Entrega:** 09/04/2026

**URL de Entrega:** <https://tinyurl.com/TyR-2026-TP2>

**Objetivo:**
Familiarizar el trabajo con aplicaciones cliente/servidor y, como primer ejemplo de aplicación de la pila TCP/IP, conocer el propósito y funcionamiento del protocolo **telnet**.

Para el estudio previo de los temas se sugiere la siguiente lectura:

Modelo cliente/servidor: Capítulo 17 (hasta pagina 546) [FOR09]

Multiplexación en capas de transporte de la pila TCP/IP: ["TCP/IP Processes, Multiplexing and Client/Server Application Roles"](http://www.tcpipguide.com/free/t_TCPIPProcessesMultiplexingandClientServerApplicati.htm), y temas siguientes hasta "Common TCP/IP Applications and Assigned Well-Known and Registered Port Numbers"

Establecimiento de conexiones TCP, Negociación de 3 Vías (three way handshake): <https://www.youtube.com/watch?v=ixBAG8apsFM> (minuto 2:0 en adelante)
 
Protocolo Telnet: Capítulo 20.1 [FOR09]


# Primer parte: Creación de un modelo simple Cliente/Servidor

Utilice para esta parte de la práctica el laboratorio de práctica _kathara-lab_conf_inicial_ y configure las interfaces de _pc1_ y _pc2_ tal como lo hizo en el primer trabajo práctico de laboratorio. Verifique conectividad entre ambos hosts.

Defina un número de puerto para el proceso servidor (superior a 1024).

En el dispositivo capturador inicie la captura utilizando el comando tcpdump o tshark sobre la interfaz eth0 y redirigir la salida a un archivo en el directorio /shared para su posterior análisis. (Ej. "`tshark -i eth0 -w - > /shared/captura_nc.pcap`")

En el host _pc1_ deberá ejecutar la utilidad `nc` actuando como servidor, indicando como parámetro el número de puerto elegido. Una vez iniciado, este servicio quedará en modo de _escucha_ o _listening_. En el otro host (_pc2_) ejecute la utilidad `nc` como cliente indicando como parámetros la IP del servidor y número de puerto.

Si generó correctamente los procesos servidor y cliente, debería poder ver una especie de "chat". Intercambie varios mensajes con el otro dispositivo y finalice la conexión (en cualquiera de los host presione CTRL+C). Luego detenga la captura en el dispositivo capturador (CTRL+C).

Analice la captura almacenada en el archivo utilizando `tshark` y diversos parámetros de visualización (consulte la guía de comandos provista por la materia).

a) "Extraiga" de la captura solamente los datos intercambiados a nivel aplicación y remítalos.

b)  Realice un diagrama representando el intercambio de tramas indicando las que corresponden al establecimiento de la conexión TCP, a las de transmisión de datos a nivel aplicación, y a las del cierre de la conexión TCP.

c) ¿Todas las tramas en las que identifica el protocolo TCP transportan datos de aplicación?. ¿Si no es así puede explicar el porqué?


# Segunda parte: Protocolo de acceso remoto TELNET

Instale e inicie en **Kathará** el laboratorio de Telnet provisto por los docentes, disponible en <https://github.com/redesunlu/kathara-labs/blob/main/tarballs/kathara-lab_telnet.tar.gz>

El laboratorio cuenta con dos hosts. El primer host actuará como cliente telnet (_client_), mientras que el segundo host actuará como servidor remoto de telnet (_remote_).

Asigne una dirección IP al host _cliente_ dentro de la red `172.16.0.0/24`. (puede elegir cualquiera del rango `172.16.0.1-254` exepto `172.16.0.10`)

En el dispositivo capturador inicie la captura utilizando el comando tcpdump o tshark sobre la interfaz eth0 y redirigir la salida a un archivo en el directorio /shared para su posterior análisis.  (Ej. "`tshark -i eth0 -w - > /shared/captura_telnet.pcap`")

En la terminal del host _cliente_, conéctese mediante telnet al host _remoto_, cuya dirección IP es `172.16.0.10`. Utilice el nombre de usuario `alumno` y la clave `ultrasecreta`.

Con la sesión iniciada en _remoto_, ejecute el siguiente comando respetando la sintaxis.

            who && who | openssl dgst

Copie la salida de dicho comando como resolución de este ejercicio (como texto). Añada además todos los comandos que ejecutó para lograr dicho resultado.

Salga del host remoto escribiendo el comando `exit`

Luego detenga la captura en el dispositivo capturador. Remítala en formato pcap como parte de la tarea.

Analice la captura:

a) Identifique e indique las tramas que corresponden a la transmisión de datos a nivel aplicación, cuáles a protocolos auxiliares (si existen) y al establecimiento y cierre de la conexión TCP. (referenciando por número de trama en la captura)

b) Comente las características de la información en tránsito con respecto a la confidencialidad.

### Bibliografía

[FOR09] Capítulo 17: "Introduction to the Application Layer" (hasta pagina 546)

[FOR09] Capítulo 20: "Remote Login: TELNET and SSH"

### Recursos en internet

* Para cada uno de los protocolos (TELNET, HTTP, DNS, FTP, etc.) a desarrollar a lo largo de la cursada, busque cuales son los Request For Comments (RFC) o Internet Draft que los describen, siguiendo la cadena de actualizaciones. Recurra a <http://www.faqs.org>, <http://www.rfc-editor.org>, y <http://www.ietf.org>

### Referencia

[FOR09] FOROUZAN, B.A. TCP IP Protocol Suite. McGraw-Hill Higher Education, 2009.


### Preguntas (guía de lectura)

En la capa de aplicación ¿a qué se denomina cliente y a qué servidor?.

En el stack TCP/IP, ¿cómo es posible que un protocolo de transporte brinde servicio a n procesos ejecutándose en un mismo host?.

¿Cuáles son las características y usos del protocolo telnet?.

¿Qué problemática resuelve NVT?.
