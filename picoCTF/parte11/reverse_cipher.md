### reverse_cipher
## Objetivo
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev_this). Can you reverse the flag.
## Hints
1. objdump and Gihdra are some tools that could assist with this
## Datos de acceso al nivel
## Solución
Con cat rev_this muestra `picoCTF{w1{1wq87g_9654g}`.
Descompilamos el archivo usando ghidra.

```bash
void main(void)

{

size_t sVar1;

char local_58 [23];

char local_41;

int local_2c;

FILE *local_28;

FILE *local_20;

uint local_14;

int local_10;

char local_9;

local_20 = fopen("flag.txt","r");

local_28 = fopen("rev_this","a");

if (local_20 == (FILE *)0x0) {

puts("No flag found, please make sure this is run on the server");

}

if (local_28 == (FILE *)0x0) {

puts("please run this on the server");

}

sVar1 = fread(local_58,0x18,1,local_20);

local_2c = (int)sVar1;

if ((int)sVar1 < 1) {

/* WARNING: Subroutine does not return */

exit(0);

}

local_10 = 0;

while (local_10 < 8) {

local_9 = local_58[local_10];

fputc((int)local_9,local_28);

local_10 = local_10 + 1;

}

local_14 = 8;

while ((int)local_14 < 0x17) {

if ((local_14 & 1) == 0) {

local_9 = local_58[(int)local_14] + '\x05';

}

else {

local_9 = local_58[(int)local_14] + -2;

}

fputc((int)local_9,local_28);

local_14 = local_14 + 1;

}

local_9 = local_41;

fputc((int)local_41,local_28);

fclose(local_28);

fclose(local_20);

return;

}
```

Este es un script simple que realiza algunos cambios en los caracteres de la bandera. Los caracteres del 0 al 7 se dejan como están. Los caracteres del 8 al 22 alternan entre sumar 5 y restar 2, empezando por sumar 5. `local_14` y 1 hace un AND bit a bit entre el número de iteración actual y 1. La instrucción if comprueba si es igual a `0`. Será igual a 0 cada dos iteraciones porque `&` 1 comprueba si el último bit es 0 o 1 y devuelve 1 si el último bit es 1, y de lo contrario devuelve 0. Finalmente, el último carácter (el 23) se agrega al archivo tal cual.
Ecutamos el comando [script.py](https://github.com/HHousen/PicoCTF-2019/tree/24b0981c72638c12f9a8572f81e1abbcf8de306d/Reverse%20Engineering/reverse_cipher/script.py) para invertir esta lógica y obtener la bandera.

picoCTF{r3v3rs39ba4806b}
## Notas adicionales
## Referencias
