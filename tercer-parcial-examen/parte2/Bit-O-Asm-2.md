### Bit-O-Asm-2
## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).
## Hints
1. `PTR`'s or 'pointers', reference a location in memory where values can be stored.
## Datos de acceso al nivel
## Solución
```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ wget https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
--2023-11-29 17:14:15--  https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: ‘disassembler-dump0_b.txt’

disassembler-dump0_b.txt     100%[===========================================>]     270  --.-KB/s    in 0s      

2023-11-29 17:14:18 (40.5 MB/s) - ‘disassembler-dump0_b.txt’ saved [270/270]

                                                                                                                 
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ cat disassembler-dump0_b.txt
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret

```
buscamos el eax, nos da DWORD PTR [rbp-0x4]
una línea más arriba tenemos el número hex 0x9fe1a si lo convertimos a decimal nos da 654874, intentamos meterlo al formato y efectivamente esa es la bandera.
picoCTF{654874}
## Notas adicionales
El [Sistema de nombres de dominio, o DNS](https://www.cloudflare.com/learning/dns/what-is-dns/), correlaciona los [nombres de dominio](https://www.cloudflare.com/learning/dns/glossary/what-is-a-domain-name/) con las [direcciones IP](https://www.cloudflare.com/learning/dns/glossary/what-is-my-ip-address/). Un registro de puntero de DNS (abreviado, PTR) proporciona el nombre de dominio asociado a una dirección IP. Un registro PTR de DNS es exactamente lo contrario del [registro "A"](https://www.cloudflare.com/learning/dns/dns-records/dns-a-record/), que proporciona la dirección IP asociada a un nombre de dominio.
## Referencias
[Hexadecimal to Decimal Converter (rapidtables.com)](https://www.rapidtables.com/convert/number/hex-to-decimal.html)
[¿Qué es un registro PTR de DNS? | Cloudflare](https://www.cloudflare.com/es-es/learning/dns/dns-records/dns-ptr-record/#:~:text=El%20Sistema%20de%20nombres%20de%20dominio%2C%20o%20DNS%2C,direcci%C3%B3n%20IP%20asociada%20a%20un%20nombre%20de%20dominio.)
