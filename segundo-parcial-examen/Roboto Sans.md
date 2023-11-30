### Roboto Sans
## Objetivo
The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:63195/) out.
## Datos de acceso al nivel
## Solución
Por el nombre del reto opté por agregar y buscar en el robots.txt, ahí me daba una pequeña pista. Comencé a buscar los caracteres en el CyberChef hasta que llegué a la opción From Base64, busqué todas las cadenas de caracteres al mismo tiempo y aunque obtuve indicios de que era ahí no logré dar con la bandera. Metí al CyberChef la primer cadena y obtuve un texto complejo, intenté con el flag1.txt pero no encontraba la página,
ZmxhZzEudHh0;anMvbXlmaW -----> flag1.txtjs/myfi

Con la segunda cadena obtuve un texto legible y lo puse en la barra de navegación, aquí obtuve la bandera.
anMvbXlmaWxlLnR4dA== -----> js/myfile.txt

La tercer cadena ya no la probé. 
svssshjweuiwl;oiho.bsvdaslejg ----->

picoCTF{Who_D03sN7_L1k5_90B0T5_22ce1f22}
## Notas adicionales
## Referencias
[From Base64 - CyberChef](https://cyberchef.org/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=YW5NdmJYbG1hV3hsTG5SNGRBPT0K)