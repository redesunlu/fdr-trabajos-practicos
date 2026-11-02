TPL 1 - Configuración inicial de la red del laboratorio
=======================================================

**Fecha de Entrega:** 26/03/2026

**URL de Entrega:** <https://tinyurl.com/TyR-2026-TP1>

**Objetivos:**

Conocer el procedimiento inicial y hacer habitual la práctica de configuración de un host en una red basada en el juego de protocolos TCP/IP.

Adquirir habilidades en el uso del entorno de emulación de redes Kathará.

# Primer parte: Instalación del entorno Kathará

1. Instalar el entorno de emulación de redes Kathará siguiendo la documentación de la siguiente URL:
   <https://github.com/KatharaFramework/Kathara/wiki/Installation-Guides>
2. Descargar y descomprimir el laboratorio de práctica de configuración inicial desde:
   <https://github.com/redesunlu/kathara-labs/blob/main/tarballs/kathara-lab_conf_inicial.tar.gz>
3. En una terminal de línea de comandos, dirigirse al directorio recientemente creado (que posee el archivo `lab.conf`) y ejecutar el comando  
   `kathara lstart`  
   para comprobar que es posible iniciar el laboratorio. Deberían abrirse cuatro ventanas con las terminales de los equipos _pc1_, _pc2_, _r1_, y _capturador_.

# Segunda parte: Configuración de hosts en una red - prueba de conectividad - análisis de captura

**Consignas**

Los comandos necesarios para llevar adelante la práctica se encuentran listados en el apunte respectivo de la asignatura, disponible en la web de la misma. En todos los casos, el informe a entregar debe mostrar los comandos ejecutados y las salidas obtenidas (en caso de ser una salida extensa, resaltar la parte importante). Además, se debe explicar lo que se interpreta de dicha salida y si es lo esperado en cada caso.

1. Verificar la/s interfaces de red (comúnmente llamada _placa de red_ o _NIC_) que el sistema operativo haya detectado en _pc1_ y _pc2_, y listar su información en pantalla.

    ¿Que comando utilizó?
    ¿Cual es el nombre de las interfaces?
    ¿Que parte de la salida le indicó cual es la interfaz que se encuentra conectada?
    ¿Cual es el nombre de la interfaz que se encuentra conectada a la red?

2. Configuración de interfaces de red para utilizar el protocolo TCP/IP. El paso siguiente es asignar las direcciones IP 10.4.11.11 y 10.4.11.12 a _pc1_ y _pc2_ respectivamente (la máscara de red es /24 o 255.255.255.0).

3. Verificar que es posible contactar ambos equipos de la red.

4. Cambiar la configuración de los nombres de los equipos asignandoles tyr11 y tyr12 a _pc1_ y _pc2_ respectivamente.

5. Resolución de nombres de hosts a direcciones IP.

    a. Configurar la resolución de nombres locales en ambos host con la información contenida en el puno 4.

    b. Verificar que es posible contactar ambos equipos de la red utilizando nombres de host.

6. Ver la tabla de ruteo definida en el equipo. ¿Cuáles son las redes accesibles?

7. Agregar la dirección `10.4.11.30` como ruta por defecto para acceder a otras redes. Verificar nuevamente la tabla de ruteo.

8. Realizar una captura de las PDU intercambiadas mientras se utiliza el comando `ping` para verificar conectividad con el otro equipo. Las acciones que debe realizar son:

    a. En el dispositivo _capturador_ inicie la captura utilizando el comando `tcpdump` o `tshark` sobre la interfaz `eth0` y redirigir la salida a un archivo en el directorio /shared para su posterior análisis.

    b. En _pc1_ ejecutar el comando ping para enviar a _pc2_ exactamente 3 mensajes ICMP Echo Request (consulte el manual de ping).

    c. Una vez obtenida la respuesta del comando _ping_ (deberán recibirse tres respuestas), detener la captura (finalizar el proceso _tcpdump_ o _tshark_ presionando **Ctrl+C**)

    d. Analizar el volcado del programa de captura utilizando la aplicación wireshark (o cualquier otro analizador de tráfico que permita leer archivos en formato _pcap_), representando en un gráfico ideado por usted el intercambio de mensajes. Indicar cuál es la función de cada uno identificando los datos de encabezados mas relevantes.

9. Escribir los comandos de configuración que ejecutó en los puntos 2, 4, 5 y 7 en _pc1_ y _pc2_ a los archivos `pc1.startup` y `pc2.startup` respectivamente, que están dentro del directorio del laboratorio, de manera tal que los nodos se configuren automáticamente al reiniciar el laboratorio.

**Recursos**

* Resumen de comandos: [http://bit.ly/tyr-comandos](http://bit.ly/tyr-comandos)
* Semestre Perdido. Linea de Comandos: [http://bit.ly/tyr-ms-cli](http://bit.ly/tyr-ms-cli) (versión traducida por el equipo de TyR)
* Semetre Perdido. Shell: [http://bit.ly/tyr-ms-shell](http://bit.ly/tyr-ms-shell) (versión traducida por el equipo de TyR)
* Manual de uso de Kathará <https://www.kathara.org/man-pages/kathara.1.html>
