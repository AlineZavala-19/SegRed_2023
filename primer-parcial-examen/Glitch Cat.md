### Glitch Cat
## Objetivo
Our flag printing service has started glitching!`$ nc saturn.picoctf.net 55826`

## Hints
1. ASCII is one of the most common encodings used in programming
2. We know that the glitch output is valid Python, somehow!
3. Press Ctrl and c on your keyboard to close your connection and return to the command prompt.
## Datos de acceso al nivel
alivz
Webshell
## Solución
```bash
alivz-picoctf@webshell:~$ nc saturn.picoctf.net 55826
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'

alivz-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
'picoCTF{gl17ch_m3_n07_9c42a45d}'
>>> exit()
```
## Notas adicionales
nc --> conectar a los puertos **TCP/UDP** de un host, a otros servidores usando diferentes protocolos de red.
python3 --> compilador de python.
exit() --> salir del compilador de python.
## Referencias
