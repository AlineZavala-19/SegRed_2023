### basic-mod1
## Objetivo
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/128/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
## Hints
1. Do you know what `mod 37` means?
2. `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.
## Datos de acceso al nivel
## Solución
```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ wget https://artifacts.picoctf.net/c/128/message.txt                                   
--2023-11-15 03:59:09--  https://artifacts.picoctf.net/c/128/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.85, 18.154.144.107, 18.154.144.104, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.144.85|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 84 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                   100%[===============================================>]      84  --.-KB/s    in 0s      

2023-11-15 03:59:10 (59.5 MB/s) - ‘message.txt’ saved [84/84]

                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ cat message.txt
165 248 94 346 299 73 198 221 313 137 205 87 336 110 186 69 223 213 216 216 177 138  

┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ touch script.py 
                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ sudo nano script.py                                                    
[sudo] password for kali: 
                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ nano script.py 
                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ python3 script.py
Flag: picoCTF{r0und_n_r0und_b6b25531}

```
## Notas adicionales
## Referencias
