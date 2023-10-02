### what's a net cat?
## Objetivo
Using netcat (nc) is going to be pretty important. Can you connect to `jupiter.challenges.picoctf.org` at port `25103` to get the flag?

## Hints
1. nc [tutorial](https://linux.die.net/man/1/nc)
## Datos de acceso al nivel
alivz
Webshell
## Solución
```bash
alivz-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 25103
You're on your way to becoming the net cat master
picoCTF{nEtCat_Mast3ry_d0c64587}
```
## Notas adicionales
nc --> conectar a los puertos **TCP/UDP** de un host, a otros servidores usando diferentes protocolos de red.
## Referencias
[nc(1): arbitrary TCP/UDP connections/listens - Linux man page (die.net)](https://linux.die.net/man/1/nc)