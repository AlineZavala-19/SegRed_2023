### transposition-trial
## Objetivo
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.Download the corrupted message [here](https://artifacts.picoctf.net/c/191/message.txt).
## Hints
1. Split the message up into blocks of 3 and see how the first block is scrambled
## Datos de acceso al nivel
## Solución
Primero descargué el archivo dado y efectivamente se podía distinguir que eran caracteres legibles desordenados así que busqué una página para solucionar la transposición, en la descripción menciona que los bloques eran de 3 por lo que no fue muy complicado mover las columnas para generar el texto bien legible.
The flag is picoCTF{7R4N5P051N6_15_3XP3N51V3_56E6924A}
## Notas adicionales
El **[cifrado por transposición](https://www.muyseguridad.net/2012/08/25/cifrado-por-transposicion-como-metodo-para-crear-y-recordar-contrasenas-fuertes/Cifrado%20por%20transposici%C3%B3n "http://es.wikipedia.org/wiki/Cifrado_por_transposición")** es una de las técnicas de criptografía más básicas que existen. Consiste en **intercambiar la posición de las letras de una palabra o frase siguiendo siempre un esquema bien definido**, que puede ser sencillo o muy complejo.
## Referencias
[Transposition Cipher Solver Helper (tholman.com)](https://tholman.com/other/transposition/)
[Cifrado por transposición como método para crear y recordar contraseñas fuertes » MuySeguridad. Seguridad informática.](https://www.muyseguridad.net/2012/08/25/cifrado-por-transposicion-como-metodo-para-crear-y-recordar-contrasenas-fuertes/)

