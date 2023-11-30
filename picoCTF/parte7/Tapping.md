### Tapping
## Objetivo
Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 9422`.
## Hints
1. What kind of encoding uses dashes and dots?
2. The flag is in the format PICOCTF{}
## Datos de acceso al nivel
## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ nc 2019shell1.picoctf.com 37920
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..... ---.. ...-- ----. ----- ----- ----. ---.. .---- }
┌──(kali㉿kali)-[~]
└─$ export NODE_PATH=$(npm root --quiet -g)
┌──(kali㉿kali)-[~]
└─$ node
> const chef = require("cyberchef");
> chef.fromMorseCode(".--. .. -.-. --- -.-. - ..-.").toString() + "{" + chef.fromMorseCode(" -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..... ---.. ...-- ----. ----- ----- ----. ---.. .---- ").toString() + "}"
'PICOCTF{M0RS3C0D31SFUN583900981}'
```

PICOCTF{M0RS3C0D31SFUN2683824610}
## Notas adicionales
From Morse Code -> convertir código morse.
npm install -g cyberchef --unsafe-perm=true --allow-root --> instalar el paquete de CyberChef globalmente utilizando.
## Referencias
[From Morse Code - CyberChef](https://cyberchef.org/#recipe=From_Morse_Code('Space','Line%20feed')&input=Li0tLiAuLiAtLi0uIC0tLSAtLi0uIC0gLi4tLiB7IC0tIC0tLS0tIC4tLiAuLi4gLi4uLS0gLS4tLiAtLS0tLSAtLi4gLi4uLS0gLi0tLS0gLi4uIC4uLS4gLi4tIC0uIC4uLS0tIC0uLi4uIC0tLS4uIC4uLi0tIC0tLS4uIC4uLS0tIC4uLi4tIC0uLi4uIC4tLS0tIC0tLS0tIH0)
