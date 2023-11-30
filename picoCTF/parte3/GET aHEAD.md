### GET aHEAD
## Objetivo
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:15931/](http://mercury.picoctf.net:15931/)
## Hints
1. Maybe you have more than 2 choices
2. Check out tools like Burpsuite to modify your requests and look at the responses
## Datos de acceso al nivel
## Solución
Inspeccionamos la página.
A partir de aquí vemos que el método que se usaba para el Rojo era "GET" y para el Azul era "POST". Podemos investigar más sobre estos, ya que son solicitudes HTTP diferentes.
Si nos fijamos en el título del reto "Get aHead", destaca la palabra Head, probablemente refiriéndose al método de solicitud HTTP "HEAD".
Podemos usar la herramienta Postman.
Ya en el programa seleccionamos la opción solicitar y creamos una carpeta. Insertamos el enlace del sitio y cambiamos al método HEAD y enviamos.
## Notas adicionales
## Referencias
