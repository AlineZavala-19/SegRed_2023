### where are the robots
## Objetivo
`https://jupiter.challenges.picoctf.org/problem/60915/` ([link](https://jupiter.challenges.picoctf.org/problem/60915/)) or http://jupiter.challenges.picoctf.org:60915
## Hints
1. What part of the website could tell you where the creator doesn't want you to look?
## Datos de acceso al nivel
## Solución
La mayoría de los sitios web tienen una página, a la que se puede acceder anexándola a la URL de la página en la que se encuentra, robots.txt
`https://jupiter.challenges.picoctf.org/problem/60915/robots.txt`

Usuario-agente: *

No permitir: /477ce.html

Ahora podemos reemplazar con en la URL anterior. Cuando lo hacemos y cargamos la URL, obtenemos el siguiente texto:`robots.txt``477ce.html`
`https://jupiter.challenges.picoctf.org/problem/60915/477ce.html`

[![La imagen no se muestra, así que solo te diré la bandera aquí: picoCTF{ca1cu1at1ng_Mach1n3s_477ce}](https://github.com/John-Danielsson/picoCTF_writeups/raw/main/img/robots_img.png "ROBOT ROCK")](https://github.com/John-Danielsson/picoCTF_writeups/blob/main/img/robots_img.png)
## Notas adicionales
El archivo robots.txt es un conjunto de instrucciones para los rastreadores de motores de búsqueda que les dice qué páginas pueden o no pueden solicitar de su sitio. Se utiliza principalmente para evitar que un sitio se sobrecargue con solicitudes.
## Referencias
