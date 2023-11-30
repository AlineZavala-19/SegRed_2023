## Irish-Name-Repo 1
## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/50009/` ([link](https://jupiter.challenges.picoctf.org/problem/50009/)) or http://jupiter.challenges.picoctf.org:50009. Do you think you can log us in? Try to see if you can login!

## Hints
1. There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?
2. Try to think about how the website verifies your login.
## Datos de acceso al nivel
## Solución
Cuando abrimos el sitio vemos que el contenido de la página principal no es muy útil. Sin embargo, cuando miramos la página de soporte, vemos una consulta. Esto nos indica que el sitio utiliza una base de datos SQL. Cuando vamos al inicio de sesión de administrador, podemos probar una inyección SQL básica para evitar el portal. Nuestra inyección es específicamente tener el nombre de usuario como y la contraseña como lo que sea. 

```bash
SELECT username, password FROM users WHERE username='$username' AND password='$password';
```

Cuando introducimos nuestra inyección, la consulta se convierte en:

```bash
SELECT username, password FROM users WHERE username='' OR 1=1--' AND password='';
```

Lo que está sucediendo aquí es que la consulta verifica si el nombre de usuario es igual a nada. A continuación, comprueba OR 1=1. Dado que 1 siempre va a ser igual a 1, esto devuelve true. El -- al final simplemente comenta el resto de la consulta. Esto engaña al servidor para que nos deje pasar por el portal.
## Notas adicionales
Una inyección SQL es una vulnerabilidad categorizada como crítica, la cual permite a un atacante inyectar sentencias SQL a través del(los) input(s) de un aplicativo web. Esta vulnerabilidad se puede producir automáticamente cuando un programa "arma descuidadamente" una sentencia SQL en tiempo de ejecución, o bien durante la fase de desarrollo, cuando el programador explicita la sentencia SQL a ejecutar en forma desprotegida. En cualquier caso, siempre que el programador necesite y haga uso de parámetros a ingresar por parte del usuario, a efectos de consultar una base de datos; ya que, justamente, dentro de los parámetros es donde se puede incorporar el código SQL intruso.
## Referencias
[Inyección SQL: Definición y ejemplos reales. - Backtrack Academy](https://backtrackacademy.com/articulo/inyeccion-sql-definicion-y-ejemplos)

