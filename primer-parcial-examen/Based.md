## Based
## Objetivo
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 15130`.

## Hints
1. I hear python can convert things.
2. It might help to have multiple windows open.
## Datos de acceso al nivel
alivz
Webshell
## Solución
```bash
alivz-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 15130
Let us see how data is stored
sludge
Please give the 01110011 01101100 01110101 01100100 01100111 01100101 as a word.
...
you have 45 seconds.....

Input:
sludge
Please give me the  163 154 165 144 147 145 as a word.
Input:
sludge
Please give me the 70656172 as a word.
Input:
pear
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_02167de8}
```
## Notas adicionales
01110011 01101100 01110101 01100100 01100111 01100101 = 
sludge
163 154 165 144 147 145 = sludge
70656172 = pear
## Referencias
[Binary to Text Translator (rapidtables.com)](https://www.rapidtables.com/convert/number/binary-to-ascii.html)
[Convert Octal to Text (Base8 Decoder) - B64Encode](https://b64encode.com/tools/octal-to-text/)[Hex to ASCII Text String Converter (rapidtables.com)](https://www.rapidtables.com/convert/number/hex-to-ascii.html)
