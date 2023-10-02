### PW Crack 2
## Objetivo
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.

## Hints
1. Does that encoding look familiar?
2. The `str_xor` function does not need to be reverse engineered for this challenge.
## Datos de acceso al nivel
alivz
Webshell
## Solución
```bash
alivz-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/13/level2.py
--2023-10-02 05:09:31--  https://artifacts.picoctf.net/c/13/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.93, 3.160.5.18, 3.160.5.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.93|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py                                     100%[==============================================================================================>]     914  --.-KB/s    in 0s      

2023-10-02 05:09:31 (43.0 MB/s) - 'level2.py' saved [914/914]

alivz-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
--2023-10-02 05:09:33--  https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.93, 3.160.5.71, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.93|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc                           100%[==============================================================================================>]      31  --.-KB/s    in 0s      

2023-10-02 05:09:33 (1.75 MB/s) - 'level2.flag.txt.enc' saved [31/31]

alivz-picoctf@webshell:~$ python3 level2.py
Please enter correct password for flag: 
That password is incorrect
alivz-picoctf@webshell:~$ cat level2.py | grep pw
def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ):
        decryption = str_xor(flag_enc.decode(), user_pw)
level_2_pw_check()
alivz-picoctf@webshell:~$ python3
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36)
'de76'
>>> exit()
alivz-picoctf@webshell:~$ python3 level2.py
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
```
## Notas adicionales

## Referencias
