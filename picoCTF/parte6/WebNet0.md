### WebNet0
## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

## Hints
1. Try using a tool like Wireshark.
2. How can you decrypt the TLS stream?
## Datos de acceso al nivel
## Solución
Descargamos los dos archivos https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap y https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key, y el primero lo abrimos mediante el programa Wireshark, nos vamos a Edición -> Preferencias... -> Protocols -> TLS -> RSA keys list Editar... -> + -> KeyFile Browse -> agregamos el segundo archivo dado que es una llave y damos aceptar.
Nos vamos a editar y buscar paquetes, buscamos "picoCTF", ahí mismo en el menú del buscador cambiamos la primer columna a la opción Detalles de paquete y en la cuarta columna cambiamos a la opción cadena, buscamos picoCTF.
## Flag
Pico-Flag: picoCTF{nongshim.shrimp.crackers}
## Notas adicionales
TLS --> Protocolo que encripta.
## Referencias