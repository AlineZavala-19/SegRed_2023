### information
## Objetivo
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/c28a959c5605d5f67480d5dd3a77f302/cat.jpg)
## Hints
1. Look at the details of the file.
2. Make sure to submit the flag as picoCTF{XXXXX}
## Datos de acceso al nivel
## Solución
```bash
┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ wget https://mercury.picoctf.net/static/c28a959c5605d5f67480d5dd3a77f302/cat.jpg  
--2023-11-04 23:25:14--  https://mercury.picoctf.net/static/c28a959c5605d5f67480d5dd3a77f302/cat.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 878136 (858K) [application/octet-stream]
Saving to: ‘cat.jpg’

cat.jpg                       100%[===============================================>] 857.55K  10.9KB/s    in 71s     

2023-11-04 23:26:34 (12.1 KB/s) - ‘cat.jpg’ saved [878136/878136]

┌──(kali㉿kali)-[~/SEGURIDAD7A]
└─$ exiftool cat.jpg
ExifTool Version Number         : 12.65
File Name                       : cat.jpg
Directory                       : .
File Size                       : 878 kB
File Modification Date/Time     : 2021:03:15 14:24:46-04:00
File Access Date/Time           : 2023:11:04 23:27:45-04:00
File Inode Change Date/Time     : 2023:11:04 23:27:44-04:00
File Permissions                : -rwxrwx---
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
                                        
```
picoCTF{the_m3tadata_1s_modified}
## Notas adicionales
cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9 --> picoCTF{the_m3tadata_1s_modified}
## Referencias
[From Base64 - CyberChef](https://cyberchef.org/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Wm14aFp6RXVkSGgwO2FuTXZiWGxtYVcNCmFuTXZiWGxtYVd4bExuUjRkQT09DQpzdnNzc2hqd2V1aXdsO29paG8uYnN2ZGFzbGVqZw)

