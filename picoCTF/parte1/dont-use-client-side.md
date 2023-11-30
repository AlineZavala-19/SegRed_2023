### dont-use-client-side
## Objetivo
Can you break into this super secure portal? ([link](https://jupiter.challenges.picoctf.org/problem/29835/)) or http://jupiter.challenges.picoctf.org:29835`https://jupiter.challenges.picoctf.org/problem/29835/`

## Hints
1. Never trust the client
## Datos de acceso al nivel
## Solución
Me fui al enlace dado, de ahí a inspeccionar el código fuente en Fuentes -> top -> jupiter.challenges.picoctf.org -> problem/29835 -> (índice). En ese archivo encontré la bandera, y la fui construyendo a partir de segir el split que iba de 0 a split*8 (0, split --> split, split *2 --> split *2, split *3 --> split *3, split *4 ...).
## Flag
picoCTF{no_clients_plz_7723ce}
## Notas adicionales
Es importante notar detalles como lo de la cadena de split, que implicaba formar la andera  a partir de darle seguimiento de cadena.
## Referencias
