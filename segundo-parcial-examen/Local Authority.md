### Local Authority
## Objetivo
Can you get the flag?Go to this [website](http://saturn.picoctf.net:49386/) and see what you can discover.
## Hints
1. How is the password checked on this website?
## Datos de acceso al nivel
## Solución
Nos vamos al website y nos lleva a un login, intenté con el típico admin pero no era correcto. Luego me fui a inspeccionar la página, encontré un archivo login.php  (http://saturn.picoctf.net:49386/login.php). En la barra de navegación agregué este archivo mientras tenía abierta la barra de navegación para ir notando cambios, en el apartado de código secure.js nos da el user y la contraseña.
if( username === 'admin' && password === 'strongPassword098765' ) y menciona que en ese caso el bool se irá a true. Al acceder con esta información nos da la bandera. 
picoCTF{j5_15_7r4n5p4r3n7_b0c2c9cb}
## Notas adicionales
Para acceder al login.php y poder inspeccionar el código lo tuve que hacer por medio de la barra de navegación.
## Referencias
