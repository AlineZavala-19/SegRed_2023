### rsa-pop-quiz
## Objetivo
Class, take your seats! It's PRIME-time for a quiz... `nc jupiter.challenges.picoctf.org 18821`
## Hints
1. 
## Datos de acceso al nivel
## Solución
## Notas adicionales
El algoritmo RSA es un algoritmo de criptografía asimétrica. Asimétrico en realidad significa que funciona con dos claves diferentes, es decir, clave pública y clave privada. Como su nombre lo indica, la clave pública se otorga a todos y la clave privada se mantiene privada.

c - texto cifrado
m - 
p - 
q - 
n - 
tn - 
e - 
d - 

n = p * q
tn = (p-1) * (q-1)
d = e mod inv tn    /  inverse(e,tn)

Encriptar      | : c = m^e mod n        / pow(m,e,n)

Desencriptar  : m = c^d mod n       /pow(c,d,n)s

## Referencias
[RSA (cryptosystem) - Wikipedia](https://en.wikipedia.org/wiki/RSA_(cryptosystem))