### ASCII FTW
## Objetivo
This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program.You can download the file from [here](https://artifacts.picoctf.net/c/508/asciiftw).
## Hints
1. The combined range of hex-ascii for English alphabets and numerical digits is from 30 to 7A.
2. Online hex-ascii converters can be helpful.
## Datos de acceso al nivel
## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ wget https://artifacts.picoctf.net/c/508/asciiftw   
--2023-11-29 21:32:57--  https://artifacts.picoctf.net/c/508/asciiftw
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.61, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16752 (16K) [application/octet-stream]
Saving to: ‘asciiftw’

asciiftw                     100%[===========================================>]  16.36K  17.1KB/s    in 1.0s    

2023-11-29 21:32:59 (17.1 KB/s) - ‘asciiftw’ saved [16752/16752]

                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ file asciiftw   
asciiftw: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=e1c32dace8ac1516160b771e493f5ebffcac9855, for GNU/Linux 3.2.0, not stripped
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ chmod 700 asciiftw
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ ./asciiftw      
The flag starts with 70
                                                                                                                 

┌──(kali㉿kali)-[~]
└─$ echo "70" | xxd -p -r
p                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ ghidra &
[5] 448912
                                                                                                                 
┌──(kali㉿kali)-[~]
└─$ Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true

[5]    done       ghidra

```
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ nano data.txt
                                                                                                                 
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ cat data.txt | cut -d "," -f2 | xxd -r -p
picoCTF{ASCII_IS_EASY_8960F0AF}         

data.txt -->
        00101184 c6 45 d0 70     MOV        byte ptr [RBP + local_38],0x70
        00101188 c6 45 d1 69     MOV        byte ptr [RBP + local_37],0x69
        0010118c c6 45 d2 63     MOV        byte ptr [RBP + local_36],0x63
        00101190 c6 45 d3 6f     MOV        byte ptr [RBP + local_35],0x6f
        00101194 c6 45 d4 43     MOV        byte ptr [RBP + local_34],0x43
        00101198 c6 45 d5 54     MOV        byte ptr [RBP + local_33],0x54
        0010119c c6 45 d6 46     MOV        byte ptr [RBP + local_32],0x46
        001011a0 c6 45 d7 7b     MOV        byte ptr [RBP + local_31],0x7b
        001011a4 c6 45 d8 41     MOV        byte ptr [RBP + local_30],0x41
        001011a8 c6 45 d9 53     MOV        byte ptr [RBP + local_2f],0x53
        001011ac c6 45 da 43     MOV        byte ptr [RBP + local_2e],0x43
        001011b0 c6 45 db 49     MOV        byte ptr [RBP + local_2d],0x49
        001011b4 c6 45 dc 49     MOV        byte ptr [RBP + local_2c],0x49
        001011b8 c6 45 dd 5f     MOV        byte ptr [RBP + local_2b],0x5f
        001011bc c6 45 de 49     MOV        byte ptr [RBP + local_2a],0x49
        001011c0 c6 45 df 53     MOV        byte ptr [RBP + local_29],0x53
        001011c4 c6 45 e0 5f     MOV        byte ptr [RBP + local_28],0x5f
        001011c8 c6 45 e1 45     MOV        byte ptr [RBP + local_27],0x45
        001011cc c6 45 e2 41     MOV        byte ptr [RBP + local_26],0x41
        001011d0 c6 45 e3 53     MOV        byte ptr [RBP + local_25],0x53
        001011d4 c6 45 e4 59     MOV        byte ptr [RBP + local_24],0x59
        001011d8 c6 45 e5 5f     MOV        byte ptr [RBP + local_23],0x5f
        001011dc c6 45 e6 38     MOV        byte ptr [RBP + local_22],0x38
        001011e0 c6 45 e7 39     MOV        byte ptr [RBP + local_21],0x39
        001011e4 c6 45 e8 36     MOV        byte ptr [RBP + local_20],0x36
        001011e8 c6 45 e9 30     MOV        byte ptr [RBP + local_1f],0x30
        001011ec c6 45 ea 46     MOV        byte ptr [RBP + local_1e],0x46
        001011f0 c6 45 eb 30     MOV        byte ptr [RBP + local_1d],0x30
        001011f4 c6 45 ec 41     MOV        byte ptr [RBP + local_1c],0x41
        001011f8 c6 45 ed 46     MOV        byte ptr [RBP + local_1b],0x46
        001011fc c6 45 ee 7d     MOV        byte ptr [RBP + local_1a],0x7d


Después de descargar el archivo dado, vemos que se trata de un archivo ELF ejecutable de Linux.
Después de obtener los derechos de ejecución con el comando:
chmod 700 asciiftw --> ejecutamos el programa.
La salida 70 podría ser valor hexadecimal. Con un solo comando, podemos averiguar si nuestra suposición es correcta. Si decodificamos este valor hexadecimal a ascii, deberíamos obtener una "p", porque esa tiene que ser la primera letra de nuestra bandera.
Iniciamos ghidra, creamos un proyecto y analizamos el ejecutable dado. Lo importante es el Árbol de Símbolos y de ahí el main:
```bash
void main(void)

{
  long lVar1;
  long in_FS_OFFSET;
  
  lVar1 = *(long *)(in_FS_OFFSET + 0x28);
  printf("The flag starts with %x\n",0x70);
  if (lVar1 != *(long *)(in_FS_OFFSET + 0x28)) {
                    /* WARNING: Subroutine does not return */
    __stack_chk_fail();
  }
  return;
}
```

Cuando hacemos clic en uno de los valores hexadecimales, seremos llevados al lugar, donde estos valores se almacenan en Ensamblaje, estos los metemos al archivo data.txt y extraemos de este nuevo archivo la bandera.

## Notas adicionales
ghidra --> herramienta de ingeniería inversa.
## Referencias
