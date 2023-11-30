### Mind your Ps and Qs
## Objetivo
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/12d820e355a7775a2c9129b2622a7eb6/values)
## Hints
1. Bits are expensive, I used only a little bit over 100 to save money
## Datos de acceso al nivel
## Solución
```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ wget https://mercury.picoctf.net/static/12d820e355a7775a2c9129b2622a7eb6/values    
--2023-11-15 02:58:26--  https://mercury.picoctf.net/static/12d820e355a7775a2c9129b2622a7eb6/values
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 206 [application/octet-stream]
Saving to: ‘values’

values                        100%[===============================================>]     206  --.-KB/s    in 0s      

2023-11-15 02:58:27 (122 MB/s) - ‘values’ saved [206/206]

                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ cat values    
Decrypt my super sick RSA:
c: 843044897663847841476319711639772861390329326681532977209935413827620909782846667
n: 1422450808944701344261903748621562998784243662042303391362692043823716783771691667
e: 65537                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ python
Python 3.11.5 (main, Aug 29 2023, 15:31:31) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import inverse, long_to_bytes
>>> 
>>> c = 843044897663847841476319711639772861390329326681532977209935413827620909782846667
>>> n = 1422450808944701344261903748621562998784243662042303391362692043823716783771691667
>>> e = 65537
>>> p = 2159947535959146091116171018558446546179
>>> q = 658558036833541874645521278345168572231473 
>>> 
>>> ph1 = (p-1) * (q-1)
>>> 
>>> d = inverse(e, ph1)
>>> 
>>> m = pow(c,d,n)
>>> 
>>> print(long_to_bytes(m))
b'picoCTF{sma11_N_n0_g0od_00264570}'
>>> 

```
## Notas adicionales
## Referencias
