### WebNet1
## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.
## Hints
1. Try using a tool like Wireshark.
2. How can you decrypt the TLS stream?
## Datos de acceso al nivel
## Solución
Abrir Wireshark
Ir a Editar > Preferencias > Protocolos > lista de claves TLS > RSA
Agregar la clave a la lista.
La bandera está en la sección SSL reensamblada del paquete JFIF JPEG

picoCTF{honey.roasted.peanuts}
## Notas adicionales
## Referencias
