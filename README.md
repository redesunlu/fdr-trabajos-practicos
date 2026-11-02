Fundamentos de Redes
=======================

### Temario General - WIP -- Copiado de TyR

- Teoría Introducción, Redes y OSI
    - Slides 01 Introducción
    - Slides 02 Protocolos y OSI
    - [Guía de lectura - Introducción](./markdown/gl-introduccion.md)
- [TPL#1 Configuración inicial del laboratorio](./markdown/tpl1-configuracion-inicial.md)
- Teoría Comunicaciones de datos (modelo, señales, multiplexación)
    - Slides 03 Modelo Comunicaciones
    - Slides 04 Multiplexación
    - Slides 05 Medios
    - TP Transmisión de datos (en desuso)
- [TPL#2 Cliente-Servidor - Telnet](./markdown/tpl2-telnet.md)
- Teoría Redes y Conmutación
    - Slides 06 Redes
- [TPL#3 Servicio de Nombres (DNS)](./markdown/tpl3-dns.md)
- Teoría Capa de Enlace (1)
    - Slides 09 Capa de Enlace
- [TPL#4 Correo Electrónico](./markdown/tpl4-correo-electronico.md)
  - Ejemplo envio de correo (en desuso)
- Teoría Capa de Enlace (2) + Redes Locales (1)
    - Slides 10 Redes de Area Local
    - TP Eficiencia del enlace (en desuso)
- [TPL#5 World Wide Web - HTTP](./markdown/tpl5-http.md)
    - Temario clase teórica HTTP (en desuso)
- Teoría Redes Locales (2)
    - Guía de lectura - Enlace
- Teoría/Práctica Cableado Estructurado
    - Documento "Cableado Estructurado"
    - Documento adicional (Cableado Estructurado)
- Teoría WLANs + Resolución TPLs (y consultas)
    - Slides 10 Wireless LANs (WLANs)
- Primer parcial
- Teoría Capa de Red, IPv4, Infraestructura de Internet
    - Slides 07 Infraestructura de Internet
    - Slides 11 Capa de Red e IP
    - Slides 12 Capa de Transporte y TCP
- Práctica Subnetting, CIDR, VLSM
- Teoría Ruteo Estático / Ruteo Dinámico
    - Guía de lectura - La Capa de Red en Internet
- [Práctica Ruteo Dinámico](en desuso)
- Teoría Capa de Transporte y TCP (1)
- Teoría Capa de Transporte y TCP (2)
    - Ejercicio Control de Congestión
- Práctica DHCP y Práctica UDP
- Captura para Trabajo Práctico Integrador
- Práctica Interface de Sockets
- Teoría y Práctica IPv6
- Consultas/Ejercicios integradores
- Segundo parcial
- Recuperatorio + Expo TP Integrador
- Teoría HTTP/2.0
    - Slides 13 HTTP/2
- Guía de Estilo para la entrega de Trabajos Prácticos

#### Pasos para generar los Trabajos Prácticos en PDF

Si ya se posee una copia del repositorio

    git pull && make

Si no se posee una copia del repositorio

    git clone https://github.com/redesunlu/tyr-trabajos-practicos.git
    apt-get --no-install-recommends install \
        pandoc lmodern texlive-xetex texlive-generic-recommended \
        texlive-fonts-recommended fonts-dejavu
    git pull && make

Si se desea (re)generar sólo un documento md (y no todos), por ejemplo "seguridad.md" -> "seguridad.pdf"

    make pdf/seguridad.pdf

Los documentos generados quedan en el directorio `./pdf/`


