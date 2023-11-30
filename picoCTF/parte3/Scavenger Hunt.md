### Scavenger Hunt
## Objetivo
There is some interesting information hidden around this site [http://mercury.picoctf.net:27393/](http://mercury.picoctf.net:27393/). Can you find it?
## Hints
1. You should have enough hints to find the files, don't run a brute forcer.
## Datos de acceso al nivel
## Solución
```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ curl http://mercury.picoctf.net:39491/
<!doctype html>
<html>
  <head>
    <title>Scavenger Hunt</title>
    <link href="https://fonts.googleapis.com/css?family=Open+Sans|Roboto" rel="stylesheet">
    <link rel="stylesheet" type="text/css" href="mycss.css">
    <script type="application/javascript" src="myjs.js"></script>
  </head>

  <body>
    <div class="container">
      <header>
                <h1>Just some boring HTML</h1>
      </header>

      <button class="tablink" onclick="openTab('tabintro', this, '#222')" id="defaultOpen">How</button>
      <button class="tablink" onclick="openTab('tababout', this, '#222')">What</button>

      <div id="tabintro" class="tabcontent">
                <h3>How</h3>
                <p>How do you like my website?</p>
      </div>

      <div id="tababout" class="tabcontent">
                <h3>What</h3>
                <p>I used these to make this site: <br/>
                  HTML <br/>
                  CSS <br/>
                  JS (JavaScript)
                </p>
        <!-- Here's the first part of the flag: picoCTF{t -->
      </div>

    </div>

  </body>
</html>
```

Podemos ver aquí la primera parte de la bandera en el comentario:

```bash
<!-- Here's the first part of the flag: picoCTF{t -->
```

Segunda parte en css

```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ curl http://mercury.picoctf.net:39491/mycss.css -s | tail
    color: #111;
    display: none;
    padding: 50px;
    text-align: center;
}

#tabintro { background-color: #ccc; }
#tababout { background-color: #ccc; }
  
```

Archivo de JavaScript

```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ curl http://mercury.picoctf.net:39491/myjs.js -s | tail
    if(elmnt.style != null) {
        elmnt.style.backgroundColor = color;
    }
}

window.onload = function() {
    openTab('tabintro', this, '#222');
}

```


```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ ~/utils/web/dirsearch/dirsearch.py -u http://mercury.picoctf.net:39491/ -e *

  _|. _ _  _  _  _ _|_    v0.4.1
 (_||| _) (/_(_|| (_| )

Extensions: 1.txt | HTTP method: GET | Threads: 30 | Wordlist size: 8948

Error Log: /home/user/utils/web/dirsearch/logs/errors-21-04-05_21-06-16.log

Target: http://mercury.picoctf.net:39491/

Output File: /home/user/utils/web/dirsearch/reports/mercury.picoctf.net/_21-04-05_21-06-16.txt

[21:06:16] Starting:
[21:06:19] 200 -   62B  - /.DS_Store
[21:06:25] 200 -   95B  - /.htaccess
[21:06:25] 200 -   95B  - /.htaccess/
[21:07:24] 200 -  961B  - /index.html
[21:07:47] 200 -  124B  - /robots.txt

Task Completed

```

Flag --> `picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_f7ce8828}`
## Notas adicionales
Inspeccionar todos los archivos disponibles.
## Referencias
