### Matryoshka doll
## Objetivo
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/205adad23bf9d8303081a0e71c9beab8/dolls.jpg)

## Hints
1. Wait, you can hide files inside files? But how do you find them?
2. Make sure to submit the flag as picoCTF{XXXXX}
## Datos de acceso al nivel
## Solución
```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ wget https://mercury.picoctf.net/static/205adad23bf9d8303081a0e71c9beab8/dolls.jpg                 
--2023-10-30 23:32:33--  https://mercury.picoctf.net/static/205adad23bf9d8303081a0e71c9beab8/dolls.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 651632 (636K) [application/octet-stream]
Saving to: ‘dolls.jpg.1’

dolls.jpg.1                   100%[===============================================>] 636.36K   759KB/s    in 0.8s    

2023-10-30 23:32:43 (759 KB/s) - ‘dolls.jpg.1’ saved [651632/651632]

                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ binwalk -e dolls.jpg       

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378952, uncompressed size: 383937, name: base_images/2_c.jpg
651610        0x9F15A         End of Zip archive, footer length: 22

                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ ls    
6dd2b0ee-b32c-4b63-a728-02f087bf94d5.jpg  buildings.png           dolls.jpg.1             p1notas.txt
Actividad1docx.docx                       claselinea.txt          _dolls.jpg-1.extracted  prueba.txt
Actividad1docx.pdf                        clasesss.txt            _dolls.jpg.extracted    sclase.txt
Actividad2.docx                           dolls.jpg               HackNotes               the_numbers.png
Actividad2.pdf                            _dolls.jpg-0.extracted  message.wav             whitepages.txt
                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ cd _dolls.jpg.extracted/             
                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A/_dolls.jpg.extracted]
└─$ ls
4286C.zip  base_images
                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A/_dolls.jpg.extracted]
└─$ cd base_images/         
                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg
                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A/_dolls.jpg.extracted/base_images]
└─$ binwalk -e 2_c.jpg  

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196042, uncompressed size: 201444, name: base_images/3_c.jpg
383804        0x5DB3C         End of Zip archive, footer length: 22
383915        0x5DBAB         End of Zip archive, footer length: 22

                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg  _2_c.jpg.extracted
                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A/_dolls.jpg.extracted/base_images]
└─$ cd _2_c.jpg.extracted/  
                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ ls
2DD3B.zip  base_images
                                                                                                                      
┌──(kali㉿kali)-[~/SEGURIDAD7A/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ cd base_images        
                                                                                                                      
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg
                                                                                                                      
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ binwalk -e 3_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77650, uncompressed size: 79807, name: base_images/4_c.jpg
201422        0x312CE         End of Zip archive, footer length: 22

                                                                                                                      
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg  _3_c.jpg.extracted
                                                                                                                      
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ cd _3_c.jpg.extracted/
                                                                                                                      
┌──(kali㉿kali)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ ls
1E2D6.zip  base_images
                                                                                                                      
┌──(kali㉿kali)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ cd base_images/       
                                                                                                                      
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg
                                                                                                                      
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ binwalk -e 4_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed size: 63, uncompressed size: 81, name: flag.txt
79785         0x137A9         End of Zip archive, footer length: 22

                                                                                                                      
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg  _4_c.jpg.extracted
                                                                                                                      
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ cd _4_c.jpg.extracted
                                                                                                                      
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls
136DA.zip  flag.txt
                                                                                                                      
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ vi flag.txt

```
picoCTF{96fac089316e094d41ea046900197662}
## Notas adicionales
## Referencias