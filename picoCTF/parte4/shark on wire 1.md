## shark on wire 1
## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

## Hints
1. Try using a tool like Wireshark
2. What are streams?
## Datos de acceso al nivel
## Solución
Luego de descargar el archivo lo abrí en WireShark, los empaquetadores en los que estamos interesados son los protocolos UDP y TCP. Elegí al azar uno de esos paquetes y abrí la pestaña de datos: podemos ver que es solo una 'b', probé esto en otros paquetes pero no salía nada. Como Wireshark tiene su propio sistema de filtrado, buqué un paquete udp que contenga el formato picoCTF.
Seguí un paquete con el protocolo UDP y fui cambiando el stream hasta que en 5 estaba la bandera.

## Notas adicionales
.PCAP --> archivo Wireshark.
Wireshark es un programa de rastreo y análisis de paquetes.
## Referencias
