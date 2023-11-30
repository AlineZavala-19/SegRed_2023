## JaWT Scratchpad
## Objetivo
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/58210/` or http://jupiter.challenges.picoctf.org:58210

## Hints 
1. What is that cookie?
2. Have you heard of JWT?
## Datos de acceso al nivel
## Solución
1. Inicie sesión como Aline.
2. Obtenga el `token jwt` de la `cookie jwt`. Token de ejemplo: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiam9obiJ9._fAF3H23ckP4QtF1Po3epuZWxmbwpI8Q26hRPDTh32Y`
3. Pegué el token `jwt` en un archivo llamado `token.txt`
4. Ejecuté este comando con hashcat para descifrar el token: hashcat -`a0 -m 16500 token.txt rockyou.txt`
5. Ejecuté el mismo comando pero con --show para obtener la contraseña utilizada: `hashcat -a0 -m 16500 token.txt rockyou.txt` -`-show`
6. Pegué el token original en [https://www.jsonwebtoken.io/](https://www.jsonwebtoken.io/)
7. Escribí de password ilovepico y cambié el usuario a admin.
8. Copié y pegué el nuevo token en la `cookie jwt`
9. Solo actualicé.
picoCTF{jawt_was_just_what_you_thought_9de8e25511a8841ab9ade0aa092be116}`
## Notas adicionales
## Referencias
