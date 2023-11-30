### Pixelated
## Objetivo
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled2.png)
## Hints
1. [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
2. Think of different ways you can "stack" images
## Datos de acceso al nivel
## Solución
Primero instalamos las herramientas necesarias.
```bash
┌──(kali㉿kali)-[~]
└─$ cd /opt       
                                                                                                                  
┌──(kali㉿kali)-[/opt]
└─$ sudo wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar
[sudo] password for kali: 
--2023-11-15 03:25:42--  http://www.caesum.com/handbook/Stegsolve.jar
Resolving www.caesum.com (www.caesum.com)... 216.234.165.33
Connecting to www.caesum.com (www.caesum.com)|216.234.165.33|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 312271 (305K) [application/x-java-archive]
Saving to: ‘stegsolve.jar’

stegsolve.jar                100%[============================================>] 304.95K   199KB/s    in 1.5s    

2023-11-15 03:25:43 (199 KB/s) - ‘stegsolve.jar’ saved [312271/312271]

```

```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ wget https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled1.png
--2023-11-15 03:26:02--  https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled1.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197174 (193K) [application/octet-stream]
Saving to: ‘scrambled1.png’

scrambled1.png                100%[===============================================>] 192.55K   592KB/s    in 0.3s    

2023-11-15 03:26:04 (592 KB/s) - ‘scrambled1.png’ saved [197174/197174]

                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ wget https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled2.png
--2023-11-15 03:26:18--  https://mercury.picoctf.net/static/9f2d081f12c05202359632c1989e7927/scrambled2.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197173 (193K) [application/octet-stream]
Saving to: ‘scrambled2.png’

scrambled2.png                100%[===============================================>] 192.55K   751KB/s    in 0.3s    

2023-11-15 03:26:19 (751 KB/s) - ‘scrambled2.png’ saved [197173/197173]

                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ java -jar /opt/stegsolve.jar 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true

```
Luego de descargar los archivos, utilizamos la herramienta previamente instalada, nos genera una ventana emergente mediante la cual abrimos la primer imagen, luego le damos  a la opción Analyse --> image Combiner para combinarla con la segunda imagen. Puede resultar de esto un archivo XOR, OR, AND que no resultan en nada o en ADD que es donde encontramos la bandera. 

flag picoCTF{7188864c}
## Notas adicionales

ADD--> combinar las imágenes byte a byte
Stegsolve --> herramienta de java para el manejo de imágenes. 
## Referencias
[https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
[ctf-tools/stegsolve/install at master · zardus/ctf-tools · GitHub](https://github.com/zardus/ctf-tools/blob/master/stegsolve/install)
